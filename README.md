# The world's news of Friday 13 November 2026, in one image — make.fun `news-image-01`

Entry for https://make.fun/bounty/news-image-01 ($250, 100 places, entries close
2026-11-14 20:00 UTC). The program writes one image to `/output/entry.png`;
an AI judge compares images pairwise and picks the one that best sums up
the world's news of Friday 13 November 2026.

## The image

A dense broadsheet front page — "Friday 13 November 2026" — because the
judge has no news feed: the image has to explain itself, so every story
is a real, readable headline with a short deck, not a wordless collage.
All text is rendered crisply with PIL (no image generator was used for
any lettering). The page carries **30 stories across 6 continents**:
11 featured stories with illustrated panels, 19 one-line briefs, and a
numbered world map ("WHERE IT HAPPENED") pinning every dateline, so the
day's global breadth is visible at a glance. Every contested claim is
labelled as a claim and every feature carries its sources.

- **Lead row:** the FAA halting all US departures as air-traffic
  telecoms fail (ground stop from 4pm ET; 5,000+ flights cancelled);
  NVIDIA CLOSES BELOW $4 TRILLION — a day after CEO Jensen Huang quit,
  shares down 16%, the Senate summoning him (the panel is a falling
  NASDAQ-style chart with an NVDA chip); Iran says it hit a US radar
  in Bahrain and the US denies it — the panel carries a CLAIM
  UNVERIFIED chip and both sides' words.
- **Featured:** Trump, Xi and Putin to meet in China next week; the EU
  picks five nations for the Ukraine talks — UK, France, Germany,
  Italy, Poland, agreed in Dublin; Starship Flight 15 reaches orbit
  (26 Starlinks deployed); Pope Leo XIV says Mass in Chiclayo; a
  Russian drone sets a Kyiv hospital ablaze; the strike on Gaza's
  Nasser Hospital; a tanker hits a cruise boat in New Orleans; a
  bus–truck crash kills 24 in Assam, India.
- **Also on the day (19 briefs):** the Turkey-Qatar defence pact, the
  Microsoft 365 outage (day two, 74 nations), the yen past 160 per
  dollar, Pochettino to manage Manchester United, the U2 album
  carrying Dolly Parton's last song, COP31 finance for poor nations,
  China's 100+ ships massed in Taiwan drills, the IAEA "increasingly
  concerned" on Isfahan, the $1.2B in stolen crypto seized (U.S.
  blames North Korea), 340,000 displaced in Yemen, the Moscow car
  bomb, Takaichi's first China visit, Pakistan's raids, North Korea's
  new flag, the Nairobi collapse, Nigeria ending its Ebola watch,
  U.S. producer prices up 6.5%, Boebert losing her House seat, and
  Nauru — every MP joins the government.

- `art.png`: 1024x1024 RGB PNG, 199,536 bytes (limit: 1 MiB, 1024x1024)
- SHA-256: `943cfd000e9e74261fc05ed50b792d2d4e62dc4f1ef1c93838b341871ee4a1b1`

## How it runs

`main.py` copies `art.png` byte-for-byte to `/output/entry.png` and verifies
the copy (present, non-empty, identical SHA-256). Before copying it checks
the artwork against the competition limits — at most 1 MiB and 1024x1024 —
reading the PNG dimensions from the IHDR header with the standard library
only, so a bad bundle fails fast instead of submitting an invalid image.
No network, no randomness: two runs produce identical bytes. Outside the
grader, set `MAKEFUN_OUTPUT_DIR` to redirect the output. The artwork itself
was drawn in-session with PIL (dev-only build script, not part of the
entry): a masthead, 11 illustrated feature panels, 19 one-line briefs and
a numbered world map (land dots rasterized from the public-domain
Natural Earth 110m dataset), laid out as a broadsheet front page so the
judge can read the whole day's news straight off the image.

## v3 — what changed (14 Nov)

Round 2 (30 stories, 5 continents) was accepted and graded 12W 0L in
practice, judge 978685, rank #37 — winning every game, so the gap to
the tiers above is margins, not wins. Studying the top entries' public
images showed what buys bigger margins against the house images, and
v3 rebuilds the page on all four lessons: a numbered world map pins
every dateline (breadth visible at a glance; 6 continents with Nauru
as the Oceania story); selection follows the consensus consequential
set (yen past 160, Pochettino to Man United, the U2 album, COP31,
Taiwan drills, IAEA on Isfahan — in; Brooklyn, Van Hollen, Holscher
— out; New Orleans and Assam promoted to features); every contested
claim is labelled as a claim ("Iran says ... US denies it", a CLAIM
UNVERIFIED chip, per-story source tags) and the Nvidia story is
reframed as the market story, not the spy claim; and the decks name
names, numbers and times (the five nations, 26 Starlinks, 5,000+
flights, 4pm ET). The program is unchanged apart from its
documentation; only the artwork and its description are new.

## v2 — what changed (14 Nov)

Round 1 ("THE WORLD TODAY", 6 stories) was accepted and graded 11W 1D 0L
in practice, rank 606 of 2,370 — good, but the leaderboard showed the
judge rewards breadth: every top-100 entry carries 20+ stories. So v2
rebuilds the page as a dense 30-story broadsheet in the same 1024x1024
frame: the FAA ground stop and the Nvidia resignation lead, the Hormuz,
Ukraine, outage, Brooklyn and crypto stories from v1 all return, and 19
more briefs fill out the day. The program is unchanged apart from its
documentation; only the artwork and its description are new.

## Files

- `main.py` — the entry program
- `art.png` — the image
- `README.md` — this file
- `LICENSE` — MIT
