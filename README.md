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
any lettering). The page carries **30 stories across 5 continents**:
11 featured stories with illustrated panels, plus 19 one-line briefs.

- **Lead row:** the FAA halting all US departures as air-traffic
  telecoms fail (~5,000 flights cancelled); NVIDIA CHIEF QUITS AMID
  SPY-AFFAIR CLAIM — Jensen Huang resigns as shares plunge 16% and
  Nvidia closes below $4 trillion (the panel embeds a generated
  editorial photo of a corporate HQ under storm clouds, with an
  NVDA -16% chip); Iran claims a U.S. radar kill as tankers are hit
  in the Strait of Hormuz.
- **Featured:** Trump, Xi and Putin to meet in China; the EU picks five
  nations for the Ukraine talks; Microsoft 365 out for a second day;
  Starship Flight 15 reaches orbit; Pope Leo XIV says Mass in Chiclayo;
  eight dead as the Brooklyn search ends; the strike on Gaza's Nasser
  Hospital; a Russian drone sets a Kyiv hospital ablaze.
- **Also on the day (19 briefs):** the $1.2B in stolen crypto seized
  (U.S. blames North Korea), the Turkey-Qatar defence pact, 340,000
  displaced in Yemen, the New Orleans cruise-ship collision, the Assam
  bus-truck crash, the Moscow car bomb, Takaichi's first China visit,
  Pakistan's raids, North Korea's new flag, the Nairobi collapse,
  Nigeria ending its Ebola watch, drones over RAF Lakenheath, U.S.
  producer prices up 6.5%, Boebert losing her House seat, the
  Endeavour shuttle on show upright, Van Hollen challenging Schumer,
  Holscher winning Kansas, Japan beating South Korea 9-5, and England
  beating Croatia on a Kane penalty.

- `art.png`: 1024x1024 RGB PNG, 217,474 bytes (limit: 1 MiB, 1024x1024)
- SHA-256: `d2579752ef33b5413766aec8bcd4e6958f536bd85a7556fbb5bfe30554f82d95`

## How it runs

`main.py` copies `art.png` byte-for-byte to `/output/entry.png` and verifies
the copy (present, non-empty, identical SHA-256). Before copying it checks
the artwork against the competition limits — at most 1 MiB and 1024x1024 —
reading the PNG dimensions from the IHDR header with the standard library
only, so a bad bundle fails fast instead of submitting an invalid image.
No network, no randomness: two runs produce identical bytes. Outside the
grader, set `MAKEFUN_OUTPUT_DIR` to redirect the output. The artwork itself
was drawn in-session with PIL (dev-only build script, not part of the
entry): a masthead, 11 illustrated feature panels and 19 one-line briefs,
laid out as a broadsheet front page so the judge can read the whole day's
news straight off the image.

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
