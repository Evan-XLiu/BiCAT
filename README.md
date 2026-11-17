# BiCAT project website

This is the **website-only `gh-pages` branch**. The code branch is [`main`](https://github.com/Evan-XLiu/BiCAT/tree/main).

Live site: https://Evan-XLiu.github.io/BiCAT/

## Structure

```text
index.html                 Title, resource links, teaser, abstract, method, results, BibTeX
static/css/index.css       Responsive styles
static/images/             Figures and favicon
static/videos/             Future project videos
.nojekyll                  Publish the static files directly
```

GitHub Pages source: **Deploy from a branch → gh-pages → / (root)**. No build step or package installation is required.

## Updating the paper page

Edit `index.html` and add approved assets under `static/`. Replace the explicit placeholders with the confirmed full title, author list, affiliations, abstract, method figure, videos, results, and verified BibTeX. Turn the paper placeholder into a link only when its actual URL is available. The main branch currently contains only a README; update the code-release notice when code is released.

The initial page intentionally contains no author identities, venue claims, experimental numbers, paper links, or fabricated citation entry. Local research folders are not included in this branch.

Preview from this folder:

```sh
python3 -m http.server 8000 --bind 127.0.0.1
```

Open http://127.0.0.1:8000/ then stop the preview with Ctrl-C.

Publish edits from this website checkout:

```sh
git status
git add index.html static
git commit -m "Update BiCAT project page"
git push origin gh-pages
```

## Reference

The information architecture and warm neutral/teal academic-page styling follow [GTPlanning](https://github.com/haldunbalim/GTPlanning/tree/gh-pages): compact navigation, centered paper header, resource buttons, teaser, abstract, method, results, and BibTeX. GTPlanning credits the [Nerfies](https://nerfies.github.io/) project page template. This starter uses newly written HTML/CSS and does not copy the reference paper's text, figures, videos, result data, or author details.
