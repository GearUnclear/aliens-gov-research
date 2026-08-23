# aliens-gov-research

Research dossier on **aliens.gov** (and its sibling **alien.gov**) — two U.S. government domains
registered on **2026-03-17** by the **Executive Office of the President / White House Office** in
the wake of President Trump's February 2026 directive to release federal records on UAP / UFO /
alien material — and on what that directive actually produced.

**Read the dossier as a site: [`index.html`](index.html)** (static, no build step — serve the
repo root or open the file). Styled by [`assets/ctrl-txt.css`](assets/ctrl-txt.css), ported
directly from **[ctrltxt.com](https://ctrltxt.com)**'s design system (Sites.S1, `ctrltxt.com/src/partials/styles/`):
the Redaction + Red Hat Mono pairing, the charcoal-and-gold palette, document-strip nav,
panels/resource lists, and the homepage's per-character "declassification" title animation
(Redaction-100 → 35). Fonts are OFL-licensed and vendored in `assets/fonts/`.

## Snapshot dates

- **Rev 1 — 2026-04-27:** both domains parked (404) on WordPress VIP; purpose unknown.
- **Rev 2 — 2026-08-23:** the answer arrived, in two parts.

## TL;DR (rev 2)

- **aliens.gov went live 2026-05-28 — and it is not about UFOs.** It redirects to
  `whitehouse.gov/aliens`, an *X-Files*-styled immigration-enforcement dashboard ("THEY WALK
  AMONG US"): a live ICE arrest map, an "encounters" ticker, and an ICE tip-line button.
  "Aliens" means non-citizens. No UAP record has ever been published there.
- **The actual UAP disclosure runs through `war.gov/UFO`** under **PURSUE** (*Presidential
  Unsealing and Reporting System for UAP Encounters*): five file tranches between 2026-05-08 and
  2026-08-07 (~375–379 files, multi-GB bundles), an AARO FY2025 annual report, an ODNI
  NDA-waiver memo, a new interagency UAP Governance Board, and a UAP Science Advisory Council
  chaired by Avi Loeb.
- **The official bottom line is unchanged:** after all of it, AARO maintains no case shows
  verifiable evidence of extraterrestrial technology or beings; hundreds remain unresolved.
- **The UAP Disclosure Act passed the House** inside the FY2027 NDAA (216–212, 2026-07-22) —
  its first chamber passage — and awaits Senate action / conference.
- **Infrastructure never moved:** both domains still sit on Cloudflare NS + the Automattic
  /WordPress VIP edge (`192.0.66.230`), byte-for-byte identical April → August. The launch was
  a tenant-side redirect flip, invisible to DNS monitoring.
- **`alien.gov` (singular) remains unobserved** — no reporting documents what it serves today.

## What's in this repo

| File | What it covers |
|---|---|
| [`index.html`](index.html) | The whole dossier as a single-page site (ctrl-txt style) |
| [`timeline.md`](timeline.md) | Chronology: Feb 2026 directive → registration → launch → five PURSUE releases → NDAA vote |
| [`disclosure-releases.md`](disclosure-releases.md) | The PURSUE release catalog, institutional documents, legislative track |
| [`technical-recon.md`](technical-recon.md) | DNS, WHOIS, TLS, HTTP, hosting analysis; April capture + August re-check |
| [`news-coverage.md`](news-coverage.md) | Per-outlet coverage, March registration cycle + May–June launch cycle |
| [`expert-perspectives.md`](expert-perspectives.md) | Loeb (now inside the tent), AARO, whistleblowers, skeptics — and how the March predictions aged |
| [`open-questions.md`](open-questions.md) | April questions scored; the August open set |
| [`sources.md`](sources.md) | Every URL referenced, with access dates and reliability flags |
| [`documents/manifest.json`](documents/manifest.json) | Machine-readable document archive index (mirrored vs. link-only, with reasons) |
| [`raw/`](raw/) | Captured WHOIS, DNS (Apr + Aug), TLS, HTTP, and .gov registry rows |

## Document archive status

A mirror pass ran 2026-08-23: **0 of 14 documents could be stored** — the research container's
egress proxy blocks all .gov/.mil hosts, and the PURSUE bundles (70 MB–1.14 GB) exceed the
25 MB mirror policy regardless. Every entry in the manifest is an honest direct link with a
`reason` field (`too-large` / `egress-blocked` / `url-unconfirmed`), and the site UI badges each
one. Re-running the pass from an unrestricted network will flip eligible entries to `mirrored`
in place.

## Disclaimer

Open-source research compiled from public records and publicly available reporting. Nothing
here is from a privileged source. August page-level claims about .gov/.mil sites rest on
search-indexed reporting (the container cannot fetch those hosts directly) and are flagged
in-text. Where reporting conflicts, the dossier shows the conflict rather than pick a winner.
