# Plugin Structure
```sh
$ tree .
.
├── .github                         # GitHub workflows configurations and tools.
│   ├── scripts
│   │   └── get_link.py             # Script to get GitHub links. Should be **COPIED** when porting to other projects.
│   └── workflows
│       ├── ci.yml                  # Main CI to check syntax error for source code. Should be **COPIED** when porting to other projects.
│       ├── plugin-catalogue.yml    # Merge or modify a plugin in official MCDReforged PluginCatalogue. Should be **MODIFIED** when porting to other projects.
│       └── release.yml             # Main CI to auto-release the plugin pack artifacts. Should be **COPIED** when porting to other projects.
├── doc
│   ├── PluginStructure.md          # This documentation. Should be ****IGNORED**** when porting to other projects.
│   └── RELEASE.md                  # Release specification. Should be **COPIED** when porting to other projects.
├── src                             # Source code directory. Should be ****IGNORED**** when porting to other projects, except .gitignore
│   ├── tools                       # Tools for creating a new MCDR plugin.
│   │   ├── __init__.py             # Tools entrypoint module.
│   │   ├── plugin_meta.py          # Plugin metadata(mcdreforged.plugin.json) generator.
│   │   └── ...                     # Other tools modules.
│   ├── plugin_id                   # Plugin source code directory.
│   │   ├── __init__.py             # Plugin entrypoint module.
│   │   └── ...                     # Other plugin modules.
│   └── mcdreforged.plugin.json     # Plugin configuration file.
├── .gitignore                      # Git ignore file. Should be **MERGED** when porting to other projects.
├── check.py                        # Check the code with Ruff and Ty. Should be **COPIED** when porting to other projects.
├── clean_pycache.py                # Clean the Python cache folders. Should be **COPIED** when porting to other projects.
├── gitrepo.toml                    # Git repository configuration, will be used for CI. Should be **MODIFIED** when porting to other projects.
├── LICENSE                         # License of this project. Should be **IGNORED** when porting to other projects.
├── main.py                         # Main entry point of the tools to create a new MCDR plugin. Should be **IGNORED** when porting to other projects.
├── pyproject.toml                  # UV configuration file of this project. Should be **MODIFIED** when porting to other projects.
├── README_*.md                     # I18n README files. Should be **IGNORED** when porting to other projects.
├── README.md                       # Main README file. Should be **IGNORED** when porting to other projects.
├── setup.py                        # Init UV virtual environment to install dependencies. Should be **COPIED** when porting to other projects.
└── ...
```

## Guide for porting to other projects

> This part is mainly for AI agents, due to they may make mistakes with hallucinations that are specific to language models. For humans, you can easily make decisions.

When porting CI configurations and the code structure to other projects, there are comments in the "tree" mentioned above as suggestions.

- With **IGNORED**, it's specific to this project, not the target project you're porting to, you can read it, but do not copy or move any content. 

- With **COPIED**, it's generic template file, you can and should directly copy it to the correct place of the target project you're porting to. Some of the "should **COPIED**" files need very little modification to avoid errors,(like Python version, package commands, etc.) and you should care for the comments in them.

- With **MODIFIED**, it's a template file too but some contents of it are designed to be edited to working properly. You need make changes to the file, then porting to the target project you're managing. If the file is existing to the target project, you should solve the conflict.

- With **MERGED**, if the file is not existing in the target project, deal it with as **COPIED**, else merge the file's content with existing one.

For files need to be not **IGNORED**, you should directly copy to the target project you're porting to. **Use tools like `mv`, `cp` and do filesystem operations, instead of read content then write into.** This can help you(LLMs) mitigate hallucinations. Then you can continue modifications in your projects.

Ignore these rules may cause unexpected errors, and increase unnecessary workload.

### Extra tips for AI agents

- For **doc/PRMessage.md**, do not modify "Additional Informations" section. It contains instructions for using [this template repository](https://github.com/Mooling0602/uv-template-for-mcdr-plugin), if you change something to other projects, that puzzles will be caused.
