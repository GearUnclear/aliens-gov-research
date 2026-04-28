# aliens-gov-research

Research dossier on **aliens.gov** (and its sibling **alien.gov**) — two U.S. government domains
registered on **2026-03-17** by the **Executive Office of the President / White House Office**, in the
wake of President Trump's February 2026 directive to release federal records on UAP / UFO / alien
material.

As of the snapshot date below, neither domain hosts a public website. The dossier collects
everything that can be learned about them right now from open sources: registry data, DNS, TLS,
hosting forensics, news coverage, and expert prediction.

## Snapshot date

All data captured **2026-04-27** unless noted. Re-run the recon script (see
[`technical-recon.md`](technical-recon.md)) to refresh.

## TL;DR

- **Domains:** `aliens.gov`, `alien.gov`
- **Created:** 2026-03-17 18:55:49 UTC (`aliens.gov`) / 2026-03-17 18:57:00 UTC (`alien.gov`)
- **Sponsoring agency (per CISA `dotgov-data` CSV):** Executive Office of the President — White
  House Office, Washington, DC
- **Registry contact org (WHOIS):** Cybersecurity and Infrastructure Security Agency
  *(this is the .gov registry, not the sponsor — every .gov shows this)*
- **Nameservers:** `ernest.ns.cloudflare.com`, `wally.ns.cloudflare.com` (Cloudflare)
- **A record:** `192.0.66.230` (Automattic, Inc. — WordPress.com / WordPress VIP)
- **TLS cert presented:** Let's Encrypt cert for `*.go-vip.co` — a **WordPress VIP Enterprise** SAN
- **HTTP response:** `404` from nginx with HSTS preload set; HTTP→HTTPS redirect in place
- **SPF:** `v=spf1 -all` (no mail authorized — anti-spoofing posture)
- **DNSSEC:** unsigned

The forensic picture: the domains are **parked on WordPress VIP Enterprise**, the same managed
hosting platform that has historically hosted whitehouse.gov. That's a strong signal the eventual
site is intended to be a CMS-driven WordPress property, not a static file dump or a bare API
endpoint.

## What's in this repo

| File | What it covers |
|---|---|
| [`timeline.md`](timeline.md) | Chronological events from Trump's Feb 2026 directive through registration and afterward |
| [`technical-recon.md`](technical-recon.md) | DNS, WHOIS, TLS, HTTP, hosting analysis with reproducible commands |
| [`news-coverage.md`](news-coverage.md) | Per-outlet summary of coverage (DefenseScoop, 404 Media, Newsweek, Vice, AV Club, etc.) |
| [`expert-perspectives.md`](expert-perspectives.md) | Avi Loeb's predictions; what scientists and AARO insiders are saying |
| [`open-questions.md`](open-questions.md) | What is still unknown — the things to watch for |
| [`sources.md`](sources.md) | Every URL referenced, with access date |
| [`raw/`](raw/) | Captured WHOIS, DNS, TLS, HTTP responses, and the relevant rows of CISA's `dotgov-data` registry |

## Disclaimer

This is open-source research compiled from public records and publicly available news reporting.
Nothing here is from a privileged source. Where reporting conflicts (e.g. on whether the registrant
is "the White House", "EOP", or "CISA"), the dossier shows the conflict rather than pick a winner.
