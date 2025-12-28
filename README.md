# Python project template

An opinionated [Copier](https://copier.readthedocs.io/en/stable/) template for Python projects managed by [uv](https://docs.astral.sh/uv/).

## Features

* CLI and autocompletion with [Typer](https://typer.tiangolo.com/).
* Rust extensions with [maturin](https://www.maturin.rs/).
* Pre-configured tools for code formatting, quality analysis, documentation and testing:
  * [ruff](https://github.com/charliermarsh/ruff)
  * [mypy](https://mypy.readthedocs.io/) or [ty](https://docs.astral.sh/ty/)
  * [pytest](https://docs.pytest.org/en/stable/)
  * [sphinx](https://sphinx-doc.org/) ([furo theme](https://pradyunsg.me/furo/))
  * [pip-audit](https://pypi.org/project/pip-audit/)
* Task automation with [just](https://github.com/casey/just).
* Support for [GitHub actions](https://github.com/features/actions) and [GitHub pages](https://pages.github.com/).

## Quickstart

To install Copier, please follow the installation instructions [here](https://copier.readthedocs.io/en/stable/#installation).

Then, to create a new project based on this template, run:

```bash
copier copy 'https://github.com/vivienm/copier-python' path/to/your/project
```

and fill in the form.

Go to the project directory and run the tests:

```bash
just ci
```

You are now ready to start coding!

Later on, if this template evolves and you want to update your project, run:

```bash
copier update --skip-answered
```
