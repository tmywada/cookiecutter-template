.PHONY: setup clean lint format help test cleanup

PYTHON_VERSION := {{ cookiecutter.python_version }}
POETRY_VERSION := {{ cookiecutter.poetry_version }}
VENV_DIR = .venv
FILE_NAME_SH = run.sh

setup: ## Create a virtual environment and install Poetry
	python -m venv $(VENV_DIR) && \
	$(VENV_DIR)/bin/pip install --upgrade pip && \
	$(VENV_DIR)/bin/pip install poetry==$(POETRY_VERSION) && \
	$(VENV_DIR)/bin/poetry install
	@if [ -f ./$(FILE_NAME_SH) ]; then \
		rm -f $(FILE_NAME_SH); \
	fi; \
	touch $(FILE_NAME_SH); \
	chmod 777 $(FILE_NAME_SH); \
	printf "source $(VENV_DIR)/bin/activate" > $(FILE_NAME_SH); \
	echo ""; \
	echo "to activate virtual environemnt"; \
	echo "		source run.sh"

validate-versions: ## Validate Python and Poetry versions
	@echo "Python version: $(PYTHON_VERSION)"
	@echo "Poetry version: $(POETRY_VERSION)"

cleanup: ## Remove virtual environment and other build artifacts
	@rm -rf $(VENV_DIR) dist $(FILE_NAME_SH)

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
