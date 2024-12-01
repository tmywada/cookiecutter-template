# {{cookiecutter.project_name}}

{{cookiecutter.project_name}} is a Python project for {{cookiecutter.description}}.

## 1. Setup Base Environment
### 1.1. Clone the Repository
```bash
git clone <repository_url>
cd {{cookiecutter.project_name}}
```

### 1.2. Set Up the Virtual Environment
```bash
make setup PYTHON_VERSION=pythonX.YY
```
Replace X.YY with your desired Python version, e.g., 3.12.

### 1.3. Cleanup Virtual EEnvironment
To remove the virtual environment, cache files, and build artifacts, run:
```bash
make cleanup
```
This removes:

* The virtual environment directory (i.e., `.venv`).

* Temporary files like `.mypy_cache` and `.pytest_cache`.

* Build artifacts such as `*.egg-info`, `build/`, and `dist/`.

## 1.4. Validate Versions
To validate the Python and Poetry versions being used, run:
```bash
make validate-versions
```
This outputs the currently configured versions of Python and Poetry.

## 2. Python Script Development
### 2.1. Add Required Packages
Add any required packages using the following command:
```bash
poetry add Z
```
Where Z is the name of the package. This will update the `[tool.poetry.dependencies]` section in the `pyproject.toml` file. For development-only dependencies, use:
```bash
poetry add --dev Z
```
This updates the [tool.poetry.dev-dependencies] section in the `pyproject.toml` file..

### 2.2. Script Location
Python scripts should be in the following folders:

* `src/<package_name>`: For core functionality of the package.

* `src/<package_name>/utils`: For utility functions or helper scripts.

## 5. Unit Tests
Run the following command to conduct unit tests:
```bash
make tests
```

## 3. Python Script Standardization
### 3.1. Linting
Run the following command to check and fix linting issues based on the configuration in `pyproject.toml`:
```bash
make lint
```
This uses `Ruff` to ensure the code adheres to the defined rules.

### 3.2. Formatting
Run the following command to format the code according to the style guide:
```bash
make format
```
This uses `Black` to format the code as per the specified rules in `pyproject.toml`.

## 4. TBD


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
