# MaMe-Re: Manga Meme Reply Selection Benchmark

Paper: <https://arxiv.org/abs/2602.15842>

## Overview

MaMe-Re is a benchmark for evaluating whether models can select a humorous
manga-panel reply to a given everyday utterance (context). Manga panels are
taken from *Give My Regards to Black Jack* (ブラックジャックによろしく) by
SHUHO SATO (available at <https://densho810.com/free/>), and each
context–panel pair is scored by human annotators for funniness.

## Files

```text
.
├── image.csv    # Meme candidates (manga panels): 400 entries
├── context.csv  # Contexts (utterances to reply to): 250 entries
├── score.csv    # Human funniness scores: 100,000 pairs (250 × 400)
└── images/      # Manga panel images: 400 PNG files
```

### `image.csv` — 400 entries

| Column | Description |
| --- | --- |
| `id` | Meme ID (0–399) |
| `text` | Dialogue text appearing in the manga panel (Japanese) |
| `description` | Text description of the panel (characters, tone, etc.) |

### `context.csv` — 250 entries

| Column | Description |
| --- | --- |
| `id` | Context ID (0–249) |
| `text` | Japanese text of an everyday utterance or situation |

### `score.csv` — 100,000 entries

| Column | Description |
| --- | --- |
| `image_id` | Meme ID (matches `image.csv`) |
| `context_id` | Context ID (matches `context.csv`) |
| `score` | Fraction of annotators who judged the pair funny (0.0–1.0) |

### `images/` — 400 files

Named `{id}.png`, where `id` matches `image.csv` (e.g. `images/0.png`).

## Annotation

Annotations were collected via crowdsourcing. Each task presented a context
paired with a manga panel and asked whether the panel is a funny reply to
the context (binary choice). Each of the 100,000 pairs received 5 responses
from a pool of 2,325 annotators, and `score` is the fraction of "funny"
responses.

## License

This repository contains two categories of content under different terms.
See [NOTICE](NOTICE) for details.

- **Manga panel images (`images/`) and the dialogue column (`text`) of
  `image.csv`**: Give My Regards to Black Jack SHUHO SATO
  (ブラックジャックによろしく　佐藤秀峰). Redistributed under the author's
  free secondary-use declaration, which permits reuse (including
  commercial) with this credit line. Any use must also comply with the
  author's secondary-use terms, including their restrictions
  (<https://densho810.com/free/>).
  These are **not** covered by CC BY 4.0.
- **All other data (`context.csv`, `score.csv`, and the `id` /
  `description` columns of `image.csv`)**: licensed under
  [CC BY 4.0](LICENSE).

## Citation

```bibtex
@misc{kohita2026memele,
  title         = {Memes-as-Replies: Can Models Select Humorous Manga Panel
                   Responses?},
  author        = {Ryosuke Kohita and Seiichiro Yoshioka},
  year          = {2026},
  eprint        = {2602.15842},
  archivePrefix = {arXiv},
  url           = {https://arxiv.org/abs/2602.15842}
}
```

## Authors

- Ryosuke Kohita (CyberAgent AI Lab)
- Seiichiro Yoshioka (CyberAgent AI Lab)
