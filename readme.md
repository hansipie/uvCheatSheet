# uv Cheat Sheet

## **Installation:**

- **Standalone Installer:**

  ```bash
  # On macOS and Linux
  curl -LsSf https://astral.sh/uv/install.sh | sh

  # On Windows
  powershell -ExecutionPolicy ByPass -c "irm https://astral.sh/uv/install.ps1 | iex"
  ```

- **Using `pip`:**

  ```bash
  pip install uv
  ```

- **Using `pipx`:**

  ```bash
  pipx install uv
  ```

- **Using Homebrew:**

  ```bash
  brew install uv
  ```

## **Basic Commands:**

- **Initialize a New Project:**

    ```bash
    uv init project_name
    ```

    This creates a new directory with essential files, including `pyproject.toml`.

    Set python version:

    ```bash
    uv init --python x.xx project_name 
    ```


  By default, this creates a virtual environment in the `.venv` directory of the project.

- **Add a Dependency to the Project:**

  ```bash
  uv add package_name
  ```

  This adds the specified package to the project's dependencies in `pyproject.toml` and updates the `uv.lock` file.

- **Remove a Dependency from the Project:**

  ```bash
  uv remove package_name
  ```

  This removes the package from the project's dependencies and updates the configuration files accordingly.

- **Synchronize the Environment with Defined Dependencies:**

  ```bash
  uv sync
  ```

  This installs all dependencies specified in `pyproject.toml` and `uv.lock` into the virtual environment.

- **Install a Specific Python Version:**

    ```bash
    uv python install 3.12
    ```

    Display the list of available Python versions:

    ```bash
    uv python list
    ```


- **Install and Use Command-Line Tools with `uv`:**

    ```bash
    uv tool install tool_name
    ```

    Run a tool directly:

    ```bash
    uv tool run tool_name
    ```

    Upgrade a tool:

    ```bash
    uv tool upgrade tool_name
    ```

    Add tools to the shell's PATH:

    ```bash
    uv tool update-shell
    ```

    Uninstall a tool:

    ```bash
    uv tool uninstall tool_name
    ```

- **Run a command or script in the Virtual Environment:**
      
    ```bash
    uv run command|script.py
    ```


## **Advanced Commands:**

- **Upgrade a Package to the Latest Version:**

  ```bash
  uv upgrade package_name
  ```

  This command updates the specified package to the latest version available.

- **Upgrade All Packages to the Latest Versions:**

  ```bash
  uv upgrade --all
  ```

    This command updates all packages in the project to their latest versions.

- **Write requirements.txt File:**

  ```bash
   uv pip compile .\pyproject.toml -o .\requirements.txt
  ```

  This command generates a `requirements.txt` file containing the project's dependencies.

## **Bonus Tips:**

- **Display dependencies in a tree structure:**

    ```bash
    uv tree
    ```

This command displays the project's dependencies in a tree structure, helping you understand their relationships.

*Note: For more detailed information, refer to the [official `uv` documentation](https://docs.astral.sh/uv/).*
