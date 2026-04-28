# Timeline

All times UTC unless noted. Sources for each entry are in [`sources.md`](sources.md).

## 2022

- **Jul 2022** — Department of Defense establishes the **All-domain Anomaly Resolution Office
  (AARO)** to consolidate UAP investigations across the services and intelligence community.

## February 2026

- **2026-02-19 / 2026-02-20** — President Donald Trump publicly directs federal agencies to
  identify and release government records relating to UAP, UFOs, and "alien and extraterrestrial
  life." Trump's stated rationale is "the tremendous interest shown" by the public. He says he
  personally does not know whether aliens are real.
- **2026-02-25** — Defense Secretary Pete Hegseth (referred to in some reporting as "Secretary of
  War") publicly commits the Pentagon to complying with Trump's directive. AARO's caseload is
  reported to exceed **2,000 UAP cases**, none of which AARO insiders say have been demonstrated
  to involve non-human technology.

## March 2026

- **2026-03-17 18:55:49 UTC** — `aliens.gov` is created in the .gov registry. Sponsoring
  organization recorded as **Executive Office of the President / White House Office,
  Washington DC** (per CISA's published `dotgov-data` registry).
- **2026-03-17 18:57:00 UTC** — `alien.gov` is created **71 seconds later**, with identical
  sponsoring organization.
- **2026-03-18 ~06:30 ET** — A Bluesky bot that monitors federal domain registrations surfaces
  the new entries. 404 Media is the first outlet to report on them publicly.
- **2026-03-18** — DefenseScoop, Newsweek, Vice, AV Club, NewsNation, and Detroit News pick up
  the story. White House principal deputy press secretary **Anna Kelly** responds with the
  statement *"Stay tuned!"* accompanied by a smiling-alien emoji. Pentagon spokesperson declines
  to comment and refers questions to the White House.
- **2026-03-18** — CISA Acting Executive Assistant Director **Chris Butera** clarifies on the
  record that *"CISA does not generally review or audit how government organizations use their
  registered domains and does not control content on all .gov websites."* — i.e., CISA's role is
  registry operator, not content owner.
- **2026-03-22 18:55:49 UTC** — The .gov registry record for `aliens.gov` is updated (5 days
  after creation). The `alien.gov` record is updated at 18:57:00 the same day. Updates of this
  kind typically reflect changes to nameservers or contacts; the public record does not say
  exactly what changed, but by this point both domains are pointed at Cloudflare nameservers
  (`ernest.ns.cloudflare.com` / `wally.ns.cloudflare.com`).

## April 2026

- **2026-04-01 07:42:58 UTC** — The cisagov/dotgov-data GitHub mirror's nightly job at
  commit `e614cf3` first publishes both `aliens.gov` and `alien.gov` rows in the public CSV.
  (Lag between registration and CSV publication is ~2 weeks.)
- **2026-04-27 (snapshot date)** — Both domains continue to resolve. They are parked on
  **WordPress VIP Enterprise** infrastructure (Automattic IP `192.0.66.230`, TLS SAN
  `*.go-vip.co`). HTTPS returns `404` from nginx; HSTS preload is set; HTTP redirects to
  HTTPS. No public site content yet.

## What hasn't happened (as of snapshot)

- No public launch of either domain.
- No formal announcement from the White House, DHS/CISA, the Pentagon, or AARO about the
  domains' intended purpose.
- No public release of UAP records *to these domains* (the National Archives continues
  publishing UAP records on a rolling statutory basis on its own properties, per CNN reporting).
