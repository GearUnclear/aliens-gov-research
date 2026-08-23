# Open questions

The dossier captures everything currently knowable from open sources. These are the questions
that the open record cannot yet answer — i.e., the things to keep watching.

## Scorecard, 2026-08-23 — the April questions, answered

| # | April question | Verdict |
|---|---|---|
| 1 | Primary records, summaries, or press materials? | **None of the above.** aliens.gov publishes ICE arrest data; UAP records went to war.gov/UFO (PURSUE). |
| 2 | A public UAP reporting portal? | **No** — the site's only reporting mechanism is an ICE tip line for reporting *people*. |
| 3 | Will alien.gov serve a different purpose? | **Still unknown** — no reporting documents what the singular domain serves today. |
| 4 | Who in the White House owns it? | Partially answered: launched and promoted by the White House itself (official X/Facebook accounts); no named program office. |
| 5 | Who reviews content for declassification? | Answered for the *real* pipeline: PURSUE Task Force + UAP Governance Board (ODNI/FBI/DoW) + AARO; Loeb's Science Advisory Council advises without clearances. |
| 6 | Launch date? | **2026-05-28** (teased 05-27). |
| 7 | When does DNS get repointed? | **Never did** — the Automattic edge simply started answering with a redirect to whitehouse.gov/aliens. The "cert change as launch signal" hypothesis was wrong: launch happened with no observable DNS change. |
| 8 | DNSSEC? | Still unsigned as of 2026-08-23. |
| 9 | Mail? | SPF still `v=spf1 -all` as of 2026-08-23. |
| 10 | Does the rollout disclose anything new? | Mixed: PURSUE's five tranches exceed the statutory-rolling-release baseline in volume, but per AARO (and Loeb) contain nothing that changes any official assessment. |
| 11 | Anything contradicting AARO's no-NHI position? | **No** — position formally restated in the FY2025 annual report. |

## Content & purpose

1. **Will aliens.gov publish primary records, or only summaries / press materials?** AARO and
   the National Archives already publish UAP records on their own properties. aliens.gov could
   duplicate, supersede, or merely link to those.
2. **Will it be a public reporting portal** (citizens submit UAP sightings) — competing with /
   replacing existing AARO and FAA reporting paths?
3. **Will alien.gov serve a different purpose** from aliens.gov, or just redirect? They're
   provisioned identically today.

## Operations

4. **Who in the White House owns the project?** The CISA registry just says "White House
   Office." Office of Science and Technology Policy? Office of Digital Strategy? AARO seconded
   to the White House?
5. **Who reviews content for declassification?** ODNI? AARO? Agency-level FOIA offices? A new
   body?
6. **What's the launch date?** No public commitment exists.

## Technical

7. **When does DNS get repointed off the WordPress VIP placeholder?** A change from the wildcard
   `*.go-vip.co` cert to a domain-specific cert is the cleanest signal of imminent launch.
8. **Will DNSSEC be enabled?** Currently unsigned. For a high-disinformation-risk site, signed
   delegation is the responsible default; absence at launch would be a finding.
9. **Will mail be enabled, or will SPF stay `-all`?** A communications portal that accepts no
   inbound mail and sends none is unusual.

## Political

10. **Does the rollout actually disclose anything new?** Per the Senate aide quoted by UFONews,
    Trump's directive may not require any disclosure beyond what statute already mandates.
11. **Does aliens.gov reveal anything that contradicts AARO's standing public position** that no
    UAP case has been demonstrated to involve non-human technology?

## Open questions, August 2026 edition

1. **What does `alien.gov` (singular) actually serve?** The one domain-level question that
   survived the launch. Needs a first-hand fetch from an unrestricted network.
2. **Does the UAP Disclosure Act survive conference?** House-passed (H.R. 8800, 216–212);
   Senate's S.Amdt. 6344 unresolved. Enactment would create the Review Board and 25-year
   presumptive-disclosure clock — the first structural change with legal force.
3. **What happens to Grusch's IG complaint** about alleged off-books DIA funding — and does the
   ODNI NDA-waiver memo actually produce new internal reporting within its 30-day POC window
   (deadline ~2026-08-30)?
4. **Will PURSUE Release 06 sustain the ~monthly cadence** (next expected early September), and
   does any tranche ever include material AARO classifies as genuinely anomalous rather than
   unresolved?
5. **Does the UAP Governance Board ever get a public charter** (Federal Register notice), and
   does Loeb's council ever get clearances or a budget?
6. **Does NARA's RG 615 collection accession the PURSUE material**, and on what lag? (No NARA
   release was confirmed inside the May–Aug window.)
7. **The aliens.gov data-quality question:** why does the site's "encounters" ticker undercount
   vs. the Deportation Data Project — methodology, lag, or curation?

## Things to monitor

- **war.gov/UFO:** new tranche announcements (pattern: `war.gov/medialink/ufo/<MMDDYY>/…`);
  the release CSV manifests.
- **congress.gov:** FY2027 NDAA conference report — search for UAPDA/Title XVIII language.
- **aaro.mil:** case-resolution reports; any revision to the "no verifiable evidence" line.
- **DNS (both domains):** still worth a periodic capture — an A-record move off `192.0.66.230`
  or a first-party TLS cert would signal a real (non-redirect) site build-out.
- **`alien.gov`:** HTTP behavior — the last unobserved surface of the original story.
- **Press briefings:** Leavitt/Kelly podium remarks; Hegseth statements; AARO releases.
- **GitHub:** the [cisagov/dotgov-data](https://github.com/cisagov/dotgov-data) repo's nightly
  diff for changes to `aliens.gov` / `alien.gov` rows.
