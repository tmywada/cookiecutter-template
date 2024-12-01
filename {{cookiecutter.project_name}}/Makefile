.PHONY: setup clean lint format help test cleanup

PYTHON_VERSION := {{ cookiecutter.python_version }}
POETRY_VERSION := {{ cookiecutter.poetry_version }}
VENV_DIR = .venv

setup: ## Create a virtual environment and install Poetry
	$(PYTHON_VERSION) -m venv $(VENV_DIR)
	$(VENV_DIR)/bin/pip install --upgrade pip
	$(VENV_DIR)/bin/pip install poetry==$(POETRY_VERSION)
	$(VENV_DIR)/bin/poetry env use $(PYTHON_VERSION)
	$(VENV_DIR)/bin/poetry install

validate-versions: ## Validate Python and Poetry versions
	@echo "Python version: $(PYTHON_VERSION)"
	@echo "Poetry version: $(POETRY_VERSION)"

cleanup: ## Remove virtual environment and other build artifacts
	rm -rf $(VENV_DIR) .mypy_cache .pytest_cache *.egg-info build dist

lint:  ## Run Ruff linter on the codebase
	$(VENV_DIR)/bin/poetry run ruff .

format:  ## Format code using Black
	$(VENV_DIR)/bin/poetry run black .

test: ## Run tests
	$(VENV_DIR)/bin/poetry run pytest

help: ## Show help for each Makefile target
	@echo "Usage: make [target]"
	@echo
	@grep -E '^[a-zA-Z_-]+:.*?## .*$$' $(MAKEFILE_LIST) | \
		awk 'BEGIN {FS = ":.*?## "}; {printf "%-15s %s\n", $$1, $$2}'
