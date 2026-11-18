# BiCAT project website

Website-only `gh-pages` checkout. Code lives at https://github.com/MAGICLAB-NUS/BiCAT.

## Structure

- `index.html` — single-page site (hero, rollout reel + key numbers, teaser, abstract, idea, method, real-world videos, baseline comparison, simulation charts, analysis, limitations, BibTeX).
- `static/css/index.css` — all styles. Colours follow the paper: teal `#1F6676` = left arm, orange `#C96A2B` = right arm; baselines are neutral grey.
- `static/js/main.js` — scroll reveals, visible-only video autoplay, task switcher for the side-by-side comparison, and the charts. **All numbers are hard-coded from the manuscript tables** (`sec/4_experiment.tex`): simulation table, efficiency table, ablation table, real-world table.
- `static/videos/rollouts/` — web versions of the real-world rollouts (H.264, 720p tall, no audio, faststart), named `<robot>_<task>_<method>.mp4` with `method ∈ {bicat, oat, fast}`.
- `static/videos/posters/` — first-frame posters for each clip.
- `static/images/`, `static/paper-assets/` — figure previews and original PDFs.
- `source-materials/previous-site/` — the earlier version of `index.html`, `index.css` and `favicon.svg`.

## Video sources

| Web file | Source |
|---|---|
| `so101_block_bicat` | `untitled folder 2/so101/block.MOV` |
| `so101_block_{fast,oat}` | `untitled folder 3/so101/{FAST,OAT}_block.MOV` |
| `g1_bottle_bicat` | `untitled folder 2/g1/bottle.MOV` |
| `g1_bottle_{fast,oat}` | `untitled folder 3/g1/{FAST,OAT}_bottle.MOV` |
| `g1_plate_bicat` (paper task "Bowl") | `untitled folder 2/g1/plate.MOV` |
| `g1_plate_{fast,oat}` | `untitled folder 3/g1/{FAST,OAT}_plate.MOV` |
| `yam_pen_bicat` | `untitled folder 2/yam/pen.mov` |
| `yam_box_bicat` | `untitled folder 2/yam/box.mov` |
| `yam_bottle_bicat` | `untitled folder 2/yam/IMG_4849.mov` |
| `yam_{pen,box,bottle}_{fast,oat}` | `untitled folder 3/YAM/{FAST,OAT}_{pen,box,bottle}.mov` |
| `ball_bicat`, `ball_fast` | `untitled folder 2/ball/` — converted but **not used on the page** |

Re-encode command used for every clip:

```sh
ffmpeg -i SRC -an -vf "scale=-2:720:flags=lanczos:out_range=tv,format=yuv420p" \
  -c:v libx264 -preset veryfast -crf 24 -profile:v high -movflags +faststart OUT.mp4
```

Clips are stored at real-time speed; the page plays them at 2× by default and labels the speed. The comparison player has 1× / 2× / 4×.

## Local preview

```sh
cd '/Users/xuanwei/MAGIC Lab/BiCAT/BiCAT_website'
python3 -m http.server 8765 --bind 127.0.0.1
```

Open http://127.0.0.1:8765/ (videos need an HTTP server; opening the file directly may block them).

## Still to fill in

- Paper / arXiv link (the hero button shows "Paper · soon").
- Final BibTeX (current entry is a placeholder `@misc`).

No commit, push or deployment has been made from this update.
