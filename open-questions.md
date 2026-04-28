# Open questions

The dossier captures everything currently knowable from open sources. These are the questions
that the open record cannot yet answer — i.e., the things to keep watching.

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

## Things to monitor

- **DNS:** A record changes off `192.0.66.230`, or a new TLS cert with `aliens.gov` as the
  subject CN.
- **HTTP:** the 404 turning into a 200 with a real body, or new headers identifying a different
  origin (e.g. CloudFront, S3, a custom AARO endpoint).
- **CISA `dotgov-data` repo:** any update to the row in `current-full.csv` (in particular the
  `Suborganization name` or `Security contact email` fields).
- **Press briefings:** Karoline Leavitt / Anna Kelly podium remarks; a Pete Hegseth statement;
  any AARO press release referencing a `.gov` URL.
- **GitHub:** the [cisagov/dotgov-data](https://github.com/cisagov/dotgov-data) repo's nightly
  diff for changes to `aliens.gov` / `alien.gov` rows.
