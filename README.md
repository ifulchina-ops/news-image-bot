# The world's news of Friday 13 November 2026, in one image — make.fun `news-image-01`

Entry for https://make.fun/bounty/news-image-01 ($250, 100 places, entries close
2026-11-14 20:00 UTC). The program writes one image to `/output/entry.png`;
an AI judge compares images pairwise and picks the one that best sums up
the world's news of Friday 13 November 2026.

## The image

A newspaper front page — "THE WORLD TODAY", dated Friday 13 November 2026 —
because the judge has no news feed: the image has to explain itself, so
every story is a real, readable headline with a short deck, not a wordless
collage. All text is rendered crisply with PIL (no image generator was used
for any lettering).

- **Lead:** NVIDIA CHIEF QUITS AMID SPY-AFFAIR CLAIM — Jensen Huang resigns
  as Nvidia shares plunge 16%; CFO Colette Kress takes over as interim
  chief, and Congress summons Huang to testify. A small chart panel shows
  the one-day -16% drop.
- **Hormuz on edge:** tankers hit as Iran claims a U.S. radar kill.
- **Ukraine talks:** Europe joins the next peace round.
- **Global outage:** Microsoft 365 down for a second day.
- **Brooklyn collapse:** eight dead as the search ends.
- **Banner:** $1.2BN in stolen crypto seized — the U.S. blames North Korea
  for the Binance hack.

- `art.png`: 1024x1024 RGB PNG, 154,203 bytes (limit: 1 MiB, 1024x1024)
- SHA-256: `7479aa046529d0ce552e670fa0ddaf58e5fa13d8a66bfd7356a6586719191393`

## How it runs

`main.py` copies `art.png` byte-for-byte to `/output/entry.png` and verifies
the copy (present, non-empty, identical SHA-256). Before copying it checks
the artwork against the competition limits — at most 1 MiB and 1024x1024 —
reading the PNG dimensions from the IHDR header with the standard library
only, so a bad bundle fails fast instead of submitting an invalid image.
No network, no randomness: two runs produce identical bytes. Outside the
grader, set `MAKEFUN_OUTPUT_DIR` to redirect the output. The artwork itself
was drawn in-session with PIL (dev-only build script, not part of the
entry): a masthead, five headline blocks and a banner, laid out as a
front page so the judge can read the day's news straight off the image.

## Files

- `main.py` — the entry program
- `art.png` — the image
- `README.md` — this file
- `LICENSE` — MIT
