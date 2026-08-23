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

## May 2026

- **2026-05-01** — The Department of War stands up the **PURSUE Task Force** (*Presidential
  Unsealing and Reporting System for UAP Encounters*) to coordinate identification, review, and
  release of UAP records across the intelligence community — the actual implementation vehicle
  for Trump's February directive.
- **2026-05-08** — **PURSUE Release 01** goes live at **war.gov/UFO**: reported as 162 files
  (120 PDFs, 28 videos, 14 images) covering 400+ incidents from 1944–2026, sourced from
  DoD/DoW, FBI, NASA, and State. Highlights: 1947–1968 flying-disc reports, Gemini 7 "bogey"
  audio, Apollo-era imagery. The downloadable bundle is ~1.14 GB (262 files). Portal traffic
  reportedly exceeds 1.7 billion hits. **The UAP records went to war.gov — not aliens.gov.**
- **2026-05-15** — Reps. Anna Paulina Luna and Eric Burlison privately review classified UAP
  video files alongside AARO Director Jon Kosloski (following Luna's March–April demand for 46
  classified videos and a missed Pentagon deadline).
- **2026-05-22** — **PURSUE Release 02**: 64 files (6 PDFs, 7 audio — the first PURSUE audio —
  51 videos), including Lake Huron F-16 shootdown footage. Documents bundle ~70 MB; video
  bundle reported at ~5.3 GB.
- **2026-05-27** — Rep. Burlison sends legislative interrogatories / document-preservation
  demands to **MITRE Corporation** covering UAP records dating to 1930 and alleged
  crash-retrieval / reverse-engineering material.
- **2026-05-27 (evening)** — The official White House account posts a ~10-second teaser video to
  X and Facebook: a UFO searchlight sweeping a border-wall structure, captioned **"They walk
  among us."**
- **2026-05-28** — **aliens.gov goes live — as an immigration-enforcement site.** The domain
  redirects to **whitehouse.gov/aliens**: an *X-Files*-styled page ("THEY WALK AMONG US" over a
  starfield) wrapping a live ICE arrest map, an "encounters" ticker, and a "Report Suspicious
  Aliens" ICE tip-line button. "Aliens" here means non-citizens, not extraterrestrials. The
  April forensic guess (WordPress-VIP-hosted CMS property) is vindicated on infrastructure and
  upended on content.
- **2026-05-29 → 06-03** — Backlash cycle: immigrant-rights groups and UAP-disclosure advocates
  alike condemn the bait-and-switch (Ross Coulthart: a "puerile effort"); conservative outlets
  frame it as successful trolling; NPR flags that the site's arrest ticker appears to
  *undercount* vs. the Deportation Data Project; CNN and Just Security publish
  rhetoric/dehumanization analyses.

## June 2026

- **2026-06-02→04** — CBS News/YouGov poll (n=2,023): **84%** say the government knows more
  about UFOs than it's telling; 21% believe extraterrestrials have visited Earth.
- **2026-06-09** — Capitol Hill press conference: Reps. Burlison, Moskowitz, Luna, and Burchett
  with whistleblower **David Grusch**, who alleges billions in hidden DIA "slush fund" spending
  on off-books UAP programs and files an Inspector General complaint.
- **2026-06-12** — **PURSUE Release 03**: 72 files (53 documents, 10 images, 6 videos, 3 audio)
  from FBI (29), CIA (18), DoW (12), NASA (11); includes a CIA Harare disc report and a 1949
  Army flying-saucer study. Documents bundle ~826 MB. Same day: Steven Spielberg's
  disclosure-premise thriller *Disclosure Day* opens.
- **2026-06-16** — ODNI, FBI, and DoW establish the interagency **UAP Governance Board**
  (announced only via written statement to two independent journalists — no Federal Register
  notice found).
- **2026-06-17** — The **UAP Science Advisory Council** forms under **Avi Loeb**, reporting to
  the Governance Board: unpaid, unbudgeted, and — per Loeb himself — without classified access.
  Membership drawn heavily from Loeb's Galileo Project orbit; skeptic Michael Shermer included.
- **2026-06-25** — **Disclosure Forum 2026** in the Russell Senate Office Building (Kennedy
  Caucus Room), chaired by Christopher Mellon; Sen. Gillibrand, Reps. Burlison and Burchett;
  Schumer/Rounds restate intent to reoffer the UAP Disclosure Act in the FY2027 NDAA.

## July 2026

- **2026-07-10** — **PURSUE Release 04** (smallest): 40 files; first **Department of Energy**
  material (Pantex plant sightings, 1949 Los Alamos "green fireballs"). Documents bundle ~227 MB.
- **~2026-07-15** — Sens. Schumer and Rounds file the revised **UAP Disclosure Act** as
  **S.Amdt. 6344** to the Senate FY2027 NDAA.
- **~2026-07-21** — **AARO FY2025 Consolidated Annual Report** published (months past the
  statutory deadline): 319 new reports (Jun 2024–May 2025), 114 resolved as mundane, caseload
  1,870; flags a Virginia-coast Navy mass-sighting case; reiterates **no verifiable evidence of
  extraterrestrial technology**.
- **2026-07-22** — **The House passes the FY2027 NDAA (H.R. 8800) 216–212 with Burlison's UAP
  Disclosure Act amendment attached** — a NARA UAP Records Collection, an independent Review
  Board, 25-year presumptive disclosure, contractor coverage. First time the UAPDA clears a
  chamber intact.
- **2026-07-31** — ODNI Principal Deputy DNI **Aaron Lukas** issues a preliminary guidance memo
  (ES 2026-00818): IC elements must name PURSUE points of contact within 30 days, and
  pre-existing NDAs/oaths do **not** bar reporting UAP information to AARO/PURSUE channels.
  (Public release came via Rep. Burlison's office, not ODNI.)

## August 2026

- **2026-08-07** — **PURSUE Release 05**: 41 files (22 documents, 16 videos, 3 images) from DoW,
  FBI, CIA, State, and EOP — first FBI FD-302 witness interviews with digital renderings; 2021
  Gulf of Oman mass sighting (~25 UAP during a live-fire exercise); 2002 Bagram triangle
  account. Cumulative PURSUE catalog: ~375–379 files across five tranches.
- **2026-08-06** — TIME cover feature: *"America Is Finally Taking Extraterrestrials Seriously."*
- **2026-08-23 (this snapshot)** — Fresh DNS capture: `aliens.gov` / `alien.gov` infrastructure
  unchanged since April (same Cloudflare NS, same Automattic edge, `v=spf1 -all`). The Senate
  has not completed FY2027 NDAA floor action; UAPDA reconciliation heads to conference.

## What hasn't happened (as of 2026-08-23 snapshot)

- **No UAP records have ever been published to aliens.gov or alien.gov.** The disclosure
  pipeline runs through war.gov/UFO (PURSUE), AARO, and the National Archives.
- No confirmed distinct purpose for `alien.gov` (singular); reporting documents only
  aliens.gov's redirect to whitehouse.gov/aliens.
- No AARO/PURSUE case has been officially assessed as extraterrestrial: after five releases,
  AARO's standing position — no verifiable evidence of non-human technology — is unchanged.
- No Senate passage of the FY2027 NDAA (and thus no enacted UAP Disclosure Act) yet.
- No Federal Register notice or public charter for the UAP Governance Board.

---

*Events before 2026-05 reflect the 2026-04-27 snapshot; events after were compiled 2026-08-23
from the reporting listed in [`sources.md`](sources.md).*
