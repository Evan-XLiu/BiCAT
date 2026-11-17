# BiCAT project website

Website-only `gh-pages` checkout. The code branch is `main`.

## Current local update

This checkout now contains the paper title, user-confirmed authors and NUS affiliation, manuscript abstract, teaser, method overview, simulation and real-world results, and analysis figures. The website now uses a coordinated pale blue theme. Theme colours are centralized at the start of `static/css/index.css`; figures and the institution logo retain their original colours.

These changes are local and have **not been committed, pushed, or deployed**. The public website still shows the previously published starter until a later authorized push.

## Files

- `index.html`: page content.
- `static/css/index.css`: original styles plus paper-content layouts.
- `static/images/`: web-size figure previews, NUS vector logo, and the supplied PNG reference.
- `static/paper-assets/`: all 17 original figure PDFs/PNGs from the supplied manuscript asset folder, including alternate versions. Originals are unchanged.
- `source-materials/`: relevant LaTeX text and `provenance.json` identifying content sources.
- `.nojekyll`: direct static publishing when a push is later authorized.

The source manuscript uses `teaser.png` and `method.png` for its primary figures; the website follows those versions and links their accompanying PDFs. Other figure variants are available under Resources but are not presented as the active method.

The NUS SVG is traced directly from the user-supplied PNG using VTracer. It contains vector paths, with no embedded PNG or external references. It is a traced reproduction, not an official NUS vector master. The original PNG is retained, and provenance is recorded in `source-materials/provenance.json`.

## Local preview

```sh
cd '/Users/xuanwei/MAGIC Lab/BiCAT/BiCAT_website'
python3 -m http.server 8765 --bind 127.0.0.1
```

Open http://127.0.0.1:8765/. Stop with Ctrl-C.

Paper links and final BibTeX remain pending. No publication venue or acceptance is inferred from the CVPR template. The result values come from the supplied manuscript; no additional experiments are invented.

GitHub Pages remains configured for `gh-pages` / root. A later push will publish files from this checkout. Review source materials and alternate assets before that future publication.

Page structure follows GTPlanning and its Nerfies template lineage. The HTML/CSS is written for this project.
