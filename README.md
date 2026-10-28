# Python project template

An opinionated [Copier](https://copier.readthedocs.io/en/stable/) template for Python projects managed by [uv](https://docs.astral.sh/uv/).

Generated projects require Python 3.11 or newer (3.15 by default).

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

First, install [uv](https://docs.astral.sh/uv/) and [Copier](https://copier.readthedocs.io/en/stable/#installation).

Then, to create a new project based on this template, run the following command and fill in the form:

```bash
copier copy 'https://github.com/vivienm/copier-python' path/to/your/project
```

Go to the project directory and initialize a Git repository:

```bash
cd path/to/your/project
git init
```

If you enabled `nix_flake`, use [Nix with flakes enabled](https://wiki.nixos.org/wiki/Flakes). Track the generated files and enter the development shell, which provides Python, uv and the development tools (including Rust tools for maturin):

```bash
git add .
nix develop
```

Otherwise, if you chose maturin, install Rust using rustup, then install the required components and development tools:

```bash
rustup component add rustfmt clippy
cargo install --locked cargo-audit
```

Upgrade the dependencies and update their minimum versions in `pyproject.toml`:

```bash
uv lock
uvx uv-bump
uv sync
```

If you chose the uv build backend, also update the `uv_build` requirement in `pyproject.toml` for your uv version (`uv --version`), following the [upstream recommendation](https://docs.astral.sh/uv/concepts/build-backend/#using-the-uv-build-backend).

Format the generated Python files, then run the checks:

```bash
uv run ruff format
uv run just ci
```

If you enabled `github_pages`, [configure your GitHub repository](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site) before the first push to its default branch: in **Settings → Pages → Build and deployment**, set **Source** to **GitHub Actions**. The generated workflow will then publish the project documentation.

You are now ready to start coding!

Later, to update your project as this template evolves, run:

```bash
copier update --skip-answered
```
