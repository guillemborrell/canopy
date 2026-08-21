# arXiv article

This directory contains a self-contained LaTeX version of the canopy paper.

## Files

- `main.tex` — article source
- `references.bib` and `main.bbl` — bibliography source and generated bibliography
- `figures/` — publication crops of the cited source figures
- `main.pdf` — compiled 15-page article
- `arxiv-metadata.txt` — suggested submission metadata

## Build

With [Tectonic](https://tectonic-typesetting.github.io/):

```bash
tectonic main.tex
```

Or with a conventional TeX installation:

```bash
pdflatex main
bibtex main
pdflatex main
pdflatex main
```

The checked-in PDF was built with Tectonic 0.17.0. The only build warning is a harmless underfull line in the data-availability URLs; there are no undefined citations or references.

## Prepare an arXiv upload

```bash
make arxiv
```

This creates `arxiv-source.tar.gz` containing `main.tex`, `main.bbl`, `references.bib`, and all figures. The archive deliberately excludes the compiled PDF and build intermediates.

Before submission, verify:

1. the author name, affiliation, and correspondence details;
2. the arXiv category and metadata in `arxiv-metadata.txt`;
3. permission or applicable quotation/reuse terms for figures reproduced from the cited papers;
4. whether an arXiv or journal-specific licence statement should be added.
