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

For an existing project, you can migrate the useful CI configurations and adapt the source-management structure as needed. However, we do not recommend copying the management tools, including their scripts and source code, other than `setup.py`.

> Adapt this template to your needs. The code in this repository is still in early development and its stability is not guaranteed.

## License

This project is licensed under the [GPLv3](LICENSE).
