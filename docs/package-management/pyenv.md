# pyenv Cheatsheet 🐍

A quick reference guide for managing multiple Python versions and virtual environments using `pyenv` and `pyenv-virtualenv`.

---

## 1. Core Version Management

| Command | Description |
| :--- | :--- |
| `pyenv install --list` | List all available Python versions for installation |
| `pyenv install <version>` | Install a specific Python version (e.g., `pyenv install 3.11.8`) |
| `pyenv uninstall <version>` | Uninstall a specific Python version |
| `pyenv versions` | List all Python versions installed in pyenv |
| `pyenv version` | Display the currently active Python version |

---

## 2. Setting Python Versions

| Command | Description |
| :--- | :--- |
| `pyenv global <version>` | Set the global default Python version across the entire system |
| `pyenv local <version>` | Set a project-specific Python version (creates a `.python-version` file) |
| `pyenv shell <version>` | Set the Python version for the current shell session only |
| `pyenv shell --unset` | Clear the shell-specific Python version setting |

---

## 3. Virtual Environments (`pyenv-virtualenv`)

| Command | Description |
| :--- | :--- |
| `pyenv virtualenv <python_version> <env_name>` | Create a new virtual environment (e.g., `pyenv virtualenv 3.11.8 my-env`) |
| `pyenv virtualenvs` | List all existing virtual environments |
| `pyenv activate <env_name>` | Manually activate a virtual environment |
| `pyenv deactivate` | Deactivate the current virtual environment |
| `pyenv virtualenv-delete <env_name>` | Delete a virtual environment |

---

## 4. Maintenance & Environment

| Command | Description |
| :--- | :--- |
| `pyenv rehash` | Rehash pyenv shims (run after installing new binaries/pip packages) |
| `pyenv which python` | Output the full executable path of the active Python binary |
| `pyenv update` | Update pyenv and available Python version list (via Homebrew or plugin) |
