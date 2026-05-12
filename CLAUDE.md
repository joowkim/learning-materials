# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository Purpose

Personal knowledge base for statistics, bioinformatics, and R programming. Contains two types of content:
- **Notes** (`notes/`) — written explanations, concept summaries, worked examples
- **Resources** (`resources/`) — curated link collections to courses, textbooks, and workshops

## Structure

```
notes/
  stats/          # regression, PCA, MLE, null hypothesis, linear algebra
  bioinformatics/ # edgeR/DESeq2, scRNA-seq, genetics terms, mass spec
  r/              # R language tips, dplyr
resources/
  stats-links.md
  bioinformatics-links.md
notebooks/
  PCA-test.ipynb
  images/
random.md         # miscellaneous
```

## Running the Notebook

```bash
jupyter notebook notebooks/PCA-test.ipynb
```

## Conventions

- New topics get their own `.md` file in the appropriate `notes/` subfolder; do not mix unrelated topics in one file.
- Link collections belong in `resources/`, not in `notes/`.
- Cite sources inline: `[reference](url or book title)` immediately after the relevant passage.
- Korean-language content is acceptable.
