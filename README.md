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

Go to the project directory, upgrade the dependencies, and update their minimum versions in `pyproject.toml`:

```bash
uv lock
uvx uv-bump
uv sync
```

If you chose the uv build backend, also update the `uv_build` requirement in `pyproject.toml` for your uv version (`uv --version`), following the [upstream recommendation](https://docs.astral.sh/uv/concepts/build-backend/#using-the-uv-build-backend).

Then run the tests:

```bash
just ci
```

You are now ready to start coding!

Later, to update your project as this template evolves, run:

```bash
copier update --skip-answered
```
