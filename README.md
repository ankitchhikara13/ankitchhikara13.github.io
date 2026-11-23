# Ankit Chhikara's portfolio

This repository contains my Quarto portfolio and four blog posts. The homepage opens on an original Vancouver Coast Mountains illustration with a pointer-responsive bird flock, a personal introduction and portrait, then follows a trail through my background, work areas, career highlights, career timeline, toolkit, education, field notes, and contact details. It also provides a direct download of my résumé PDF. Separate About, Blog, Résumé, and Contact pages provide more detail; the résumé page can also be printed or saved as PDF from the browser. The posts include notes on starting the UBC Master of Data Science program and exploring Vancouver, along with reproducible Python and R analyses. The Python post analyzes the Iris dataset bundled with scikit-learn; the R post analyzes the built-in `mtcars` dataset. The computational posts render their code, output, and figures from the locked project environments.

The Telstra and UBC logo assets in `images/logos/` are public-domain files from Wikimedia Commons: [Telstra](https://commons.wikimedia.org/wiki/File:Telstra_logo_(horizontal_variant).svg) and [UBC](https://commons.wikimedia.org/wiki/File:British_columbia_ca_univ_logo.svg). They are used to identify the stated work and education affiliations.

## Prerequisites

Install the following tools before building:

- [Quarto](https://quarto.org/docs/get-started/)
- [uv](https://docs.astral.sh/uv/getting-started/)
- [R](https://cran.r-project.org/) 4.6.1 or newer

The repository includes the Python version in `.python-version`, `uv.lock`, and the R lockfile in `renv.lock`. The `renv` package is bootstrapped by the project activation files.

## Build from a clean clone

Run these commands from the top level of the repository:

```sh
git clone https://github.com/ankitchhikara13/ankitchhikara13.github.io.git
cd ankitchhikara13.github.io
uv sync
Rscript -e 'renv::restore(prompt = FALSE)'
uv run quarto render
```

To view the built site locally, start Quarto's preview server:

```sh
uv run quarto preview
```

Open the URL Quarto prints, usually <http://localhost:4200>. The preview server rebuilds the site when source files change. If the port is busy, use the alternate URL Quarto prints.

## Data and network access

The Python post is `posts/iris-python/index.qmd` and uses the Iris dataset distributed with scikit-learn. The R post is `posts/mtcars-r/index.qmd` and uses `mtcars`, which ships with R. The personal posts are `posts/first-weeks/index.qmd` and `posts/exploring-vancouver/index.qmd`. No data files are downloaded at render time, and the computational posts link to the public documentation for each dataset. The initial `uv sync` and `renv::restore()` commands require internet access to download packages; after the environments are installed, rendering does not need a data-service connection.

## Re-rendering after changes

Run `uv run quarto render` from the repository root after editing any `.qmd` file. Quarto updates the generated site in `docs/`, which is the directory used for GitHub Pages deployment.


//I have used copilot to help me with the CSS and UI of this assignment/milestone .