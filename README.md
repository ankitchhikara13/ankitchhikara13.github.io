# Ankit Chhikara's portfolio

This repository contains my Quarto portfolio and four blog posts for DSCI 521: two personal posts about starting the MDS program and exploring Vancouver, plus separate computational posts using Python and R. The Python post analyzes the Iris dataset bundled with scikit-learn; the R post analyzes the built-in `mtcars` dataset. The computational posts render their code, output, and figures from the locked project environments.

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

The rendered website is written to `docs/`. Open `docs/index.html` directly, or serve it locally with:

```sh
python3 -m http.server --directory docs 8000
```

Then open <http://localhost:8000>. To preview the source files with automatic rebuilding, run:

```sh
uv run quarto preview
```

Quarto prints the preview URL, usually <http://localhost:4200>. If that port is busy, use the alternate URL Quarto prints.

## Data and network access

The Python post is `posts/iris-python/index.qmd` and uses the Iris dataset distributed with scikit-learn. The R post is `posts/mtcars-r/index.qmd` and uses `mtcars`, which ships with R. The personal posts are `posts/first-weeks/index.qmd` and `posts/exploring-vancouver/index.qmd`. No data files are downloaded at render time, and the computational posts link to the public documentation for each dataset. The initial `uv sync` and `renv::restore()` commands require internet access to download packages; after the environments are installed, rendering does not need a data-service connection.

## Re-rendering after changes

Run `uv run quarto render` from the repository root after editing any `.qmd` file. Quarto updates the generated site in `docs/`, which is the directory used for GitHub Pages deployment.


//I have used copilot to help me with the CSS and UI of this assignment/milestone .