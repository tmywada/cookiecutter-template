# {{cookiecutter.project_name}}

{{cookiecutter.project_name}} is a Python project for {{cookiecutter.description}}

## Folder Structure
```
{{cookiecutter.project_name}}/
├── data/                               # For data storage and management
│   ├── raw/                            # Raw, unprocessed data
│   ├── processed/                      # Cleaned or transformed data
│   ├── interim/                        # Intermediate data during processing
│   └── external/                       # External datasets from third-party sources
├── docs/                               # Project documentation
├── notebooks/                          # Jupyter or Colab notebooks
├── src/                                # Main Python package source code
│   └── {{cookiecutter.package_name}}/  # Python package directory
│       ├── __init__.py                 # Marks this as a Python package
│       └── utils/                      # Utility functions or scripts
│           └── __init__.py             # Marks this as a Python package
├── tests/                              # Unit tests and test scripts
├── config/                             # Configuration files for the project
├── .gitignore                          # Git ignore rules
├── pyproject.toml                      # Poetry configuration for dependency management
├── Makefile                            # Makefile for environment setup and common tasks
└── README.md                           # Project description and instructions
```

## How to use
