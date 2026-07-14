# UV Template for MCDR Plugin

中文（简体）| [English](README_en_US.md)

本项目旨在提供一个基于 [UV](https://docs.astral.sh/uv/) 的模板和工具包，帮助你通过它快速创建 MCDReforged 插件。

对于插件项目源码结构设计，请查看此[文档](doc/PluginStructure.md)。

## 推荐预装的工具

### 包管理器

- [UV](https://docs.astral.sh/uv)

> 建议使用本项目前，先阅读 UV 的文档，了解其基本概念和使用方法。

### Linter / Formatter（格式化）工具

- [Ruff](https://docs.astral.sh/ruff)

### LSP（语言服务器）

- [Ty](https://docs.astral.sh/ty)

## 用法
将此仓库克隆到本地，然后执行`main.py`运行交互式插件（源码结构）创建器。

> 如果是作为模板仓库用于开发自己的插件，建议克隆后先删除 `.git` 目录，然后重新执行 `git` 的相关命令初始化 git 仓库。
>
> 推荐先运行 `setup.py` 脚本初始化虚拟环境，以避免前置依赖安装不全的问题。

使用 `./main.py --help` 可以查看工具的详细帮助信息。

你也可以直接将本仓库作为一个模板仓库，然后根据需要修改配置和源代码，以直接创建自定义的插件项目。

对于已有的项目，你可以按需将各种有用的 CI 配置迁移过去，并改造源码管理结构，但不建议将除 `setup.py` 以外的工具（相关的脚本和代码）也搬过去。 

> 根据自己的需要灵活处理，本仓库内的代码还处于早期开发状态，并不能保证稳定。

## 协议

本项目使用 [GPLv3](LICENSE) 协议开源。
