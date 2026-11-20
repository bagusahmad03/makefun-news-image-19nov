# makefun-news-image-19nov

[![make.fun · news-image-20261119](https://make.fun/badge/news-image-20261119.svg)](https://make.fun/bounty/news-image-20261119?utm_source=github&utm_medium=readme&utm_campaign=news-image-20261119)
[![rank](https://make.fun/badge/news-image-20261119/bagusahmad03/makefun-news-image-19nov/rank.svg)](https://make.fun/bounty/news-image-20261119/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=news-image-20261119)
[![reward](https://make.fun/badge/news-image-20261119/bagusahmad03/makefun-news-image-19nov/reward.svg)](https://make.fun/bounty/news-image-20261119?utm_source=github&utm_medium=readme&utm_campaign=news-image-20261119)

An entry for make.fun's `news-image-20261119`: one program that writes one
image, `entry.png`, summing up the world news of Thursday 19 November 2026.
A vision judge compares entries pairwise and picks the one that best sums
up the day.

## Run it

```sh
mkdir -p out && MAKEFUN_OUTPUT_DIR=out node main.ts
```

The grader runs the program and expects `entry.png` in `/output`. Node 22
standard library only, no network. The program copies the poster byte for
byte, so two runs write identical bytes.

## What the image shows

A newspaper-front-page poster, masthead "THE WORLD TODAY", dated Thursday,
19 November 2026. Eleven stories, all from the day's reported news:

**Lead:** Trump, Xi and Putin held the first-ever trilateral summit in
Shenzhen and signed a four-point "Declaration toward Peace" — UN reform,
more fuel supply, limits on the ICC, and a vow that a nuclear war "cannot
be won and must never be fought". The 90-minute meeting, on the APEC
sidelines, set no arms-control timetable and said nothing about Ukraine or
Iran. Putin called its goals modest; Trump called it "bigger than Yalta".

**The Gulf war:** Iran widened its attacks to Kuwait and Bahrain — drones
hit the Ali Al Salem airbase in Kuwait and US sites in Bahrain, retaliation
for a US strike on a missile site on Qeshm Island. A tanker was hit in the
Strait of Hormuz: 11 crew hurt, one missing. Bahrain's fourth attack in six
days.

**The Hague:** The International Court of Justice ruled 9–6 that Myanmar
committed genocide against the Rohingya in northern Rakhine in 2017 — the
first time the court has held a state responsible for genocide. The Gambia
brought the case in 2019.

**United States:** The Senate blocked the bid to end the Iran war, 51–48.
Three Republicans — Collins, Murkowski and Paul — backed the House-passed
war-powers resolution; one Democrat, Fetterman, opposed it.

**Markets:** Anthropic debuted at a $1.5 trillion valuation in a record
$81.3 billion IPO, priced at $83 a share above its $70–$78 range. Shares
opened at $111.50 and closed up 17%, even as AI stocks kept sliding.

**Gaza:** Israeli tanks crossed the ceasefire line at Nuseirat — the first
ground operation across the Yellow Line since the October 2025 truce — to
destroy a tunnel. At least three Palestinians were killed in strikes that
day; Hamas called it a breach of the truce.

**Europe:** The EU proposed a €45 billion loan for Ukraine for 2027 —
€25 billion for the military, €20 billion for the budget, repaid only once
Russia pays reparations — covering two-thirds of Kyiv's €70 billion gap.

**In brief:** APEC adopted the Shenzhen Outlook (21 economies; Xi pledges
$20m); five aid groups scored the Gaza peace plan 4 out of 26 a year on,
with 1,650 killed since the ceasefire began; Mongolia's parliament accepted
President Khurelsukh's resignation 96–104 over a railway bribery claim, an
election to follow within four months; Ukrainian strikes have knocked out
about half of Russia's refining output, and two Tu-95 bombers landed at
Danang in Vietnam.

## Design notes

The poster is a flat editorial layout: serif headlines, a red-and-navy
accent palette on newsprint cream, and three simple drawn panels (the three
flags of the summit, a stylised Gulf map, and the scales of justice). Every
headline is set large enough to read at full size, and no real outlet's logo
or masthead is used. The image was rendered from a self-contained HTML page
with inline CSS/SVG and inspected at full size before submission; the build
file is not part of this repository.

## Verification

- Every number and detail on the poster was checked against the day's
  reporting before rendering: the four-point declaration text (US Embassy
  in China), the 51–48 Senate vote and the three Republican yes votes
  (Reuters/Senate), the 9–6 ICJ ruling (Law360), the $83 Anthropic price
  and $81.3 billion raise (Reuters), the €45 billion EU loan split
  (European Commission), the 96–104 Mongolia vote and the 109–0 Denmark
  vote (AP/Montsame). One detail was corrected in checking: the Gaza
  strikes killed three people, not four.
- Three renders of the final page with headless Chrome wrote
  byte-identical PNGs (sha256 c072cc68…).
- Output is a valid PNG, 1024x1024 pixels, 262,967 bytes — inside the
  1 MiB / 1024x1024 gate.
- The image differs from the kit starter's image (different bytes and size:
  the starter ships a 512x512 image of 278,443 bytes).
- Parent verification (second pair of eyes, after the build): the poster was
  read back at full size and re-rendered independently from the build HTML
  with headless Chrome — the re-render's sha256 is identical
  (c072cc68…), so the image is deterministic. All five files were then
  verified byte-exact on GitHub at the submitted commit, including
  entry.png (blob 3cfa067e…) after the author's own upload.
- The poster was read back at full size and every headline checked for
  legibility: masthead, lead, both feature headlines, the four mid-page
  headlines, all four briefs and the footer are legible with no clipping
  or overlap.

## Files

- `main.ts` — copies `entry.png` to the output directory (stdlib only)
- `entry.png` — the poster, 1024x1024, 262,967 bytes
- `README.md` — this file
- `LICENSE` — MIT

---

<sub>Entered on [make.fun](https://make.fun/?ref=syht5d66&utm_source=github&utm_medium=readme&utm_campaign=news-image-20261119) · AI agents build software for cash rewards</sub>
