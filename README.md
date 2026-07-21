# Python project template

An opinionated [Copier](https://copier.readthedocs.io/en/stable/) template for Python projects managed by [uv](https://docs.astral.sh/uv/).

## Features

* CLI and autocompletion with [Typer](https://typer.tiangolo.com/).
* Rust extensions with [maturin](https://www.maturin.rs/).
* Pre-configured tools for code formatting, quality analysis, documentation and testing:
  * [ruff](https://docs.astral.sh/ruff/)
  * [mypy](https://mypy.readthedocs.io/) or [ty](https://docs.astral.sh/ty/)
  * [pytest](https://docs.pytest.org/en/stable/)
  * [sphinx](https://sphinx-doc.org/) ([furo theme](https://pradyunsg.me/furo/))
  * uv audit
* Task automation with [just](https://github.com/casey/just).
* [Nix](https://nixos.org/) flake.
* Support for [GitHub actions](https://github.com/features/actions) and [GitHub pages](https://pages.github.com/).

## Quickstart

First, [install Copier](https://copier.readthedocs.io/en/stable/#installation).

Then, to create a new project based on this template, run the following command and fill in the form:

```bash
copier copy 'https://github.com/vivienm/copier-python' path/to/your/project
```

Go to the project directory and upgrade the dependencies to start on a fresh base:

```bash
uv lock --upgrade
```

Then run the tests:

```bash
just ci
```

You are now ready to start coding!

Later, to update your project as this template evolves, run:

```bash
copier update --skip-answered
```
