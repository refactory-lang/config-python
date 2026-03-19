# @refactory/config-python

Shared Python toolchain configuration for all [refactory-lang](https://github.com/refactory-lang) Python repositories.

## Usage

Unlike TypeScript configs which can be extended via `"extends"`, Python tooling configs are copied or referenced:

### ruff

Copy `ruff.toml` to your repo root, or reference it:

```toml
# pyproject.toml
[tool.ruff]
extend = "path/to/config-python/ruff.toml"
```

### mypy

Copy settings from `mypy.toml` into your `pyproject.toml`:

```toml
[tool.mypy]
strict = true
python_version = "3.11"
```

### pytest

Copy settings from `pytest.ini` into your `pyproject.toml`:

```toml
[tool.pytest.ini_options]
testpaths = ["tests"]
addopts = "-ra --strict-markers"
```

### pyproject.toml reference

See `pyproject.base.toml` for the complete reference configuration including build system, dependencies, and tool settings.

## What's included

| File | Purpose |
|------|---------|
| `ruff.toml` | Lint + format config (E, F, I, UP, B, SIM, ANN, RUF rules) |
| `mypy.toml` | Strict type checking config |
| `pytest.ini` | Test runner config with strict markers |
| `pyproject.base.toml` | Reference pyproject.toml with all standard settings |

## Toolchain

All refactory-lang Python repos use:

| Tool | Purpose |
|------|---------|
| `hatchling` | Build backend |
| `ruff` | Linting + formatting |
| `mypy --strict` | Type checking |
| `pyright` | Type inference (used by python-annotate) |
| `pytest` | Testing |
| Python 3.11+ | Minimum version |
