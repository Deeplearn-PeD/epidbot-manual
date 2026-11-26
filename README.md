# epidbot-manual

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.24560456.svg)](https://doi.org/10.5281/zenodo.24560456)

> 📖 **Cite this manual via its DOI:** [https://doi.org/10.5281/zenodo.24560456](https://doi.org/10.5281/zenodo.24560456)
> This DOI identifies the current release (v2.9.0); [Zenodo](https://zenodo.org) mints a fresh DOI for every tagged release.

Step-by-step user manual for [EpiDBot](https://github.com/Deeplearn-PeD/EpiDBot)
— AI-powered public health data analytics.

**Browse the manual:** https://deeplearn.ltd/epidbot-manual/

Available in English (`docs/index.md`) and Portuguese
(`docs/manual-pt.md`), with screenshots under `docs/screenshots/`.
Built with [MkDocs Material](https://squidfunk.github.io/mkdocs-material/)
and deployed to GitHub Pages automatically on every push to `main`.

## Local preview

```bash
pip install -r requirements-docs.txt
mkdocs serve
```

## PDF export

```bash
ENABLE_PDF_EXPORT=1 mkdocs build   # outputs site/EpiDBot_User_Manual.pdf
```

## Deployment

`mkdocs gh-deploy --force` runs via GitHub Actions
(`.github/workflows/deploy-manual.yml`) and publishes the built site to
the `gh-pages` branch.
