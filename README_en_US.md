# UV Template for MCDR Plugin

[中文（简体）](README.md) | English

This repository provides a [UV](https://docs.astral.sh/uv/)-based template and toolkit for quickly creating [MCDReforged](https://github.com/MCDReforged/MCDReforged) plugins.

For guidance on plugin source layouts, see [PluginStructure.md](doc/PluginStructure.md).

## Recommended Tools

### Package Manager

- [UV](https://docs.astral.sh/uv)

> Before using this template, we recommend reading the UV documentation to understand its core concepts and workflow.

### Linter / Formatter

- [Ruff](https://docs.astral.sh/ruff)

### Language Server

- [Ty](https://docs.astral.sh/ty)

## Usage

Clone this repository locally, then run `./setup.py` to create the UV environment and install dependencies. Run `./main.py` to start the interactive plugin project creator.

> If you use this repository as a template for your own plugin, remove the `.git` directory after cloning and initialize a new Git repository.

Run `./main.py --help` to see detailed help for the tool.

You can also use this repository directly as a template and customize its configuration and source code to create your own plugin project.

Check [Plugin Structure](doc/PluginStructure.md) to see how to migrate template structure and CI configurations to an already existing project.

Anyway, adapt this template to your needs. The code in this repository is still in early development and its stability is not guaranteed.

## Plugin Dependency Management

One benefit of using UV to manage MCDReforged plugin source code is that plugins can add other plugin source repositories with `uv add <url>`. This improves code completion and other development tooling.

In most cases, any plugin source repository with a valid `pyproject.toml` file can be managed by UV.

To add a plugin dependency, run:

```sh
uv add https://github.com/<author>/<repo_name>.git
```

When the upstream repository changes, update that dependency with:

```sh
uv sync --upgrade
```

This updates all dependencies that satisfy their version constraints. To update only one dependency, run `uv sync --upgrade-package <package_name>`, where `<package_name>` is the value of `[project].name` in the upstream project's `pyproject.toml`.

## License

This project is licensed under the [GPLv3](LICENSE).
