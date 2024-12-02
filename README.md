# Cookiecutter Template for Python Package Development

This repository provides a Cookiecutter template for Python package development, designed to streamline project setup and enforce best practices. It integrates `venv` for virtual environment management and leverages `Poetry` for package and dependency management.

The template reduces boilerplate code and boosts productivity, making it ideal for developers seeking a structured and reliable starting point for Python projects.


## 1. Preparation
### 1.1. Clone the Repository
Clone the template repositiry to your local machine:
```bash
git clone <repository_url>
```
This will `cookiecutter-template` folder. 

### 1.2. Check System Python Version
Verify the Python version on your system:
```bash
python --version
```
Ensure this version matches the version you intend to use for your project.

### 1.3. Execute Cookiecutter
Run the following command to create a new project:
```bash
cookiecutter cookiecutter-template
```
This command will request user inputs. They are:
* `project_name`: Name of the project.
* `package_name`: Name of Python package.
* `description`: A brief description of the package.
* `author_name`: Author's name
* `author_email`: Author's email address
* `python_version`: The system Python version.
* `poetry_version`: Poetry version (defulat is recommended).

Navigate to the newly created project directory:
```bash
cd {{ cookiecutter.project_name }}
```

## 2. Setup Base Environment
### 2.1. Create Virtual Environment
Set up the virtual environment and install dependencies:
```bash
make setup
```

### 2.2. Cleanup Environment
To remove the virtual environment and build artifacts, run:
```bash
make cleanup
```
This command removes removes:

* The virtual environment directory (`.venv`).

* Build artifacts (`dist/`).

## 2.3. Validate Versions
Verify the configured versions of Python and Poetry, run:
```bash
make validate-versions
```
This outputs the currently configured versions of Python and Poetry.

## 3. Python Script Development
### 3.1. Add Required Packages
Add dependencies using Poetry:
```bash
poetry add Z
```
Where Z is the name of the package. This will update the `[tool.poetry.dependencies]` section in the `pyproject.toml` file. For development-only dependencies, use:
```bash
poetry add --dev Z
```
This updates the [tool.poetry.dev-dependencies] section in the `pyproject.toml` file..

### 3.2. Organize Location
Python scripts should be in the following folders:

* `src/<package_name>`: For core functionality of the package.

* `src/<package_name>/utils`: For utility functions or helper scripts.

## 4. Unit Tests
Run the following command to conduct unit tests:
```bash
make tests
```

## 5. Python Script Standardization
### 5.1. Linting
Run the following command to check and fix linting issues based on the configuration in `pyproject.toml`:
```bash
make lint
```
This uses `Ruff` to ensure the code adheres to the defined rules.

### 5.2. Formatting
Run the following command to format the code according to the style guide:
```bash
make format
```
This uses `Black` to format the code as per the specified rules in `pyproject.toml`.

## 6. Package Creation
Build the package after standardizing scripts:
```bash
poetry build
```
The build artifacts (wheel and source distribution) will be generated in the `dist` folder.

## 7. TDB