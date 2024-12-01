# cookiecutter-template

Folder structure:

```
my_project/
├── data/                             # For data storage and management
│   ├── raw/                          # Raw, unprocessed data
│   ├── processed/                    # Cleaned or transformed data
│   ├── interim/                      # Intermediate data during processing
│   └── external/                     # External datasets from third-party sources
├── docs/                             # Project documentation
├── notebooks/                        # Jupyter or Colab notebooks
├── src/                              # Main Python package source code
│   └── my_package/                   # Python package directory
│       ├── __init__.py               # Marks this as a Python package
│       └── utils/                    # Utility functions or scripts
│           └── __init__.py
├── tests/                            # Unit tests and test scripts
├── config/                           # Configuration files for the project
├── .gitignore                        # Git ignore rules
├── pyproject.toml                    # Poetry configuration for dependency management
├── Makefile                          # Makefile for environment setup and common tasks
└── README.md                         # Project description and instructions
```
