After uv sync, cannot detect .venv in vs code kernel
1. Make this file: agents/.vscode/settings.json
    ```
    {
    "python.venvPath": "${workspaceFolder}",
    "python.defaultInterpreterPath": "${workspaceFolder}/.venv/bin/python"
    }
    ```
2. Install pip and ipykernel using uv:
    ```
    uv pip install --upgrade pip
    uv pip install ipykernel
    ```
3. Register the Jupyter kernal:
    ```
    uv run python -m ipykernel install --user --name="agents-venv" --display-name="Python (agents .venv)"
    ```
3. Reload VS Code and check the kernel picker. (Ctrl+Shift+P, and then type reload)
