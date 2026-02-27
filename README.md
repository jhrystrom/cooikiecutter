<p align="center">
  <img src="assets/coiikiecutter-logo.png" alt="coiikiecutter logo" width="300"/>
</p>

# coiikiecutter

A [copier](https://copier.readthedocs.io/) template for Python projects at the Oxford Internet Institute. Generates an opinionated project structure with modern tooling out of the box.

## Features

- **[uv](https://docs.astral.sh/uv/)** — fast dependency management and virtual environments
- **[ruff](https://docs.astral.sh/ruff/)** — linting and formatting
- **[ty](https://github.com/astral-sh/ty)** — type checking
- **[pytest](https://docs.pytest.org/)** — testing
- **[pre-commit](https://pre-commit.com/)** — git hooks for ruff
- **GitHub Actions CI** — lint and test on push/PR

## Requirements

- [copier](https://copier.readthedocs.io/) >= 9.0.0
- [uv](https://docs.astral.sh/uv/)

## Usage

```bash
copier copy gh:jonathanrystrom/coiikiecutter my-project
cd my-project
uv sync
```

You will be prompted for:

| Field | Description |
|---|---|
| `full_name` | Your full name |
| `email` | Your email (defaults to `firstname.lastname@oii.ox.ac.uk`) |
| `github_username` | Your GitHub username |
| `python_version` | Python version (default: `3.12`) |
| `project_name` | Human-readable project name |
| `project_slug` | Slug used for GitHub/PyPI |
| `package_name` | Python package name (valid identifier) |

## Generated project layout

```
my-project/
├── src/
│   └── my_package/
│       └── __init__.py
├── tests/
│   └── test_example.py
├── data/
├── pyproject.toml
├── ruff.toml
├── Makefile
└── .github/
    └── workflows/
        └── ci.yaml
```

## Makefile targets

```bash
make install   # uv sync
make lint      # ruff check + ruff format + ty check
make test      # pytest
```
