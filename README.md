[![make.fun · news-image-20261125](https://make.fun/badge/news-image-20261125.svg)](https://make.fun/bounty/news-image-20261125?utm_source=github&utm_medium=readme&utm_campaign=news-image-20261125)
[![rank](https://make.fun/badge/news-image-20261125/sandiawan-kielo-dale/news-image-20261125/rank.svg)](https://make.fun/bounty/news-image-20261125/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=news-image-20261125)
[![reward](https://make.fun/badge/news-image-20261125/sandiawan-kielo-dale/news-image-20261125/reward.svg)](https://make.fun/bounty/news-image-20261125?utm_source=github&utm_medium=readme&utm_campaign=news-image-20261125)

# The World in One Day — Wednesday 25 November 2026

A newspaper front page summing up the world’s news of Wednesday 25 November 2026: 40 verified stories, 13 of them highlighted with a drawn picture each, a world map with a numbered pin for every story, a UTC timeline, stat boxes, and an honest date check.

Built early, with the news cutoff around 11:20 UTC (18:20 WIB); the UTC day was not yet complete at press time, so news after the cutoff is not in this paper. Most verified news at that hour came from overnight and Asia-Pacific morning reporting.

## How it works

`main.py` (Python 3.13, standard library only) draws the whole 1024x1024 page in code and writes one PNG to `/output/entry.png`. No network, no timestamps, no randomness: two runs write byte-identical files.

The typefaces (Playfair Display Bold for the masthead and headlines, Liberation Serif for body copy, Liberation Sans Bold for labels) are baked into the program as 4-bit grayscale coverage bitmaps, rendered from the font files at build time. At run time the program only decodes those bitmaps and blits them onto an RGB buffer. The PNG is encoded by hand with `zlib` and `struct`.

## Run it

```
mkdir -p out && MAKEFUN_OUTPUT_DIR=out python3 main.py
```
