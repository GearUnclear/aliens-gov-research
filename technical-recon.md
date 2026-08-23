# Technical reconnaissance

Reproducible, OSINT-only. Every command below was run against `aliens.gov` and `alien.gov` from
this host on **2026-04-27**. Raw outputs are preserved in [`raw/`](raw/).

## 2026-08-23 re-check

A fresh DNS capture ([`raw/dns-records-2026-08-23.txt`](raw/dns-records-2026-08-23.txt), taken via
dnspython from a container without `dig`) shows the infrastructure **byte-for-byte unchanged**
since April:

| Record | 2026-04-27 | 2026-08-23 |
|---|---|---|
| `A` | `192.0.66.230` (Automattic) | `192.0.66.230` — unchanged |
| `AAAA` | `2a04:fa87:fffd::c000:42e6` | unchanged |
| `NS` | `ernest`/`wally.ns.cloudflare.com` | unchanged |
| `TXT` | `v=spf1 -all` | unchanged |
| `MX` | none | none |

The April hosting-forensic conclusion — *"the domains will host a content site, eventually,"
CMS-driven on WordPress VIP* — was **half right**. Per reporting (see
[`timeline.md`](timeline.md)), `aliens.gov` went live **2026-05-28** as a **redirect to
`whitehouse.gov/aliens`**, a WordPress-VIP-hosted White House page. The Automattic A record was
never repointed because it never needed to be: the VIP edge now answers for `aliens.gov` with a
redirect into whitehouse.gov instead of the platform 404.

*(No fresh HTTP/TLS capture accompanies the August snapshot: the research container's egress
proxy blocks direct connections to the domains. HTTP-layer behavior above is from news reporting,
not first-hand capture — flagged accordingly.)*

## Registry (WHOIS)

```bash
whois aliens.gov
whois alien.gov
```

| Field | aliens.gov | alien.gov |
|---|---|---|
| Created | 2026-03-17 18:55:49 UTC | 2026-03-17 18:57:00 UTC |
| Updated | 2026-03-22 18:55:49 UTC | 2026-03-22 18:57:00 UTC |
| Expires | 2027-03-17 | 2027-03-17 |
| Registrar | get.gov (CISA) | get.gov (CISA) |
| Registrant org | Cybersecurity and Infrastructure Security Agency | Cybersecurity and Infrastructure Security Agency |
| Admin org | Cybersecurity and Infrastructure Security Agency, 1110 N. Glebe Rd, Arlington VA 22201 | (same) |
| Admin email | help@get.gov | help@get.gov |
| Status | serverTransferProhibited | serverTransferProhibited |
| Nameservers | ernest.ns.cloudflare.com, wally.ns.cloudflare.com | (same) |
| DNSSEC | unsigned | unsigned |

> ⚠️ The WHOIS shows CISA as the registrant because CISA is the .gov registry — every .gov has
> CISA in WHOIS. The **actual sponsoring federal agency** is published separately by CISA in
> [`current-full.csv`](raw/dotgov-registry-entries.csv):
>
> ```
> alien.gov,Federal - Executive,Executive Office of the President,White House Office,Washington,DC,(blank)
> aliens.gov,Federal - Executive,Executive Office of the President,White House Office,Washington,DC,(blank)
> ```
>
> i.e. these are **EOP / White House Office** domains, not DHS or CISA program domains.

The 71-second gap between the two creation timestamps is consistent with a single human operator
clicking through the get.gov registration UI twice in a row, not two independent requests.

## DNS

```bash
for t in A AAAA NS SOA MX TXT CAA HINFO; do dig aliens.gov "$t" +noall +answer; done
```

| Record | Value | Notes |
|---|---|---|
| `A` | `192.0.66.230` | Automattic, Inc. — WordPress.com / WordPress VIP range `192.0.64.0/18` |
| `AAAA` | `2a04:fa87:fffd::c000:42e6` | Automattic IPv6 |
| `NS` | `ernest.ns.cloudflare.com`, `wally.ns.cloudflare.com` | Cloudflare authoritative DNS |
| `SOA` | `ernest.ns.cloudflare.com. dns.cloudflare.com.` | |
| `TXT` | `v=spf1 -all` | Hard SPF reject — explicitly blocks anyone (including the domain owner) from sending mail as `aliens.gov`. Pure anti-spoofing posture; not a mail-handling domain. |
| `MX` | *(none)* | No mail. |
| `HINFO` | `RFC8482 ""` | Cloudflare's RFC 8482 minimal response to ANY queries — not real host info. |

`alien.gov` resolves to the **same A/AAAA/NS** records — they share infrastructure.

## TLS

```bash
openssl s_client -connect aliens.gov:443 -servername aliens.gov </dev/null \
  | openssl x509 -noout -text
```

- **Issuer:** Let's Encrypt E7
- **Subject:** `CN = go-vip.co`
- **SANs:** `*.go-vip.co`, `go-vip.co`
- **Validity:** 2026-03-14 → 2026-06-12

This is the default platform certificate served by **WordPress VIP Enterprise** (Automattic's
managed CMS hosting). Because no WordPress VIP customer has yet attached a real cert for
`aliens.gov`, the load balancer falls back to the platform wildcard.

## HTTP

```bash
curl -I https://aliens.gov
```

```
HTTP/2 404
server: nginx
content-type: text/html; charset=utf-8
x-rq: sea4 0 30 9980
x-cache: EXPIRED
strict-transport-security: max-age=31536000;includeSubdomains;preload
```

- `nginx` + `x-rq` + `x-cache` headers match WordPress VIP's edge fingerprint.
- `x-rq: sea4` — request served from VIP's Seattle (sea4) edge.
- HSTS `max-age=31536000; includeSubdomains; preload` is set — both domains are configured to
  qualify for the HSTS preload list, so browsers will refuse to load them over plain HTTP once
  they hit the preload.
- HTTP traffic is 301-redirected to HTTPS.

## Hosting forensic conclusion

`aliens.gov` and `alien.gov` are **provisioned WordPress VIP Enterprise tenants that have not yet
been bound to content**. WordPress VIP is the same hosting platform that has historically been
used for `whitehouse.gov`. The most likely interpretation:

1. The White House Office of Digital Strategy (or its 2026 equivalent) provisioned the domains
   on existing WordPress VIP infrastructure as part of a planned launch.
2. Until DNS is repointed to a customer-specific edge cert + a published WordPress site, the
   domains will keep returning the platform 404 with the wildcard `go-vip.co` cert.

This forensic posture is **inconsistent with** several plausible-sounding alternatives:

- A pure static document mirror (would more likely use S3/CloudFront like archives.gov does).
- A pure file-drop API (no need for a CMS).
- A "prevent squatters" defensive registration with no plans to use the domain (would have left
  it parked at CISA's default holding pages, not pre-provisioned on a CMS).

The infrastructure choice suggests the domains *will* host a content site, eventually.

## Reproduce

The raw outputs in [`raw/`](raw/) were generated with:

```bash
whois aliens.gov                                                       > raw/whois-aliens-gov.txt
whois alien.gov                                                        > raw/whois-alien-gov.txt
for d in aliens.gov alien.gov; do
  for t in A AAAA NS SOA MX TXT CAA DS DNSKEY HINFO; do
    dig "$d" "$t" +noall +answer
  done
done                                                                   > raw/dns-records.txt
openssl s_client -connect aliens.gov:443 -servername aliens.gov \
  </dev/null 2>/dev/null | openssl x509 -noout -text                   > raw/tls-cert-aliens-gov.txt
for d in aliens.gov alien.gov; do
  curl -sI -k https://$d; curl -sI http://$d
done                                                                   > raw/http-headers.txt
curl -s https://raw.githubusercontent.com/cisagov/dotgov-data/main/current-full.csv \
  > raw/dotgov-current-full-2026-04-27.csv
```
