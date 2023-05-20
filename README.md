# git-hooks

1. Prerequisites

    - Before proceeding with the installation, ensure that you have the following prerequisites installed on your system:

    - Python (version 3.6 or later)
    - Git


2. Installation

    To install pre-commit, follow these steps:

    1. Open a terminal or command prompt.

    2. Install pre-commit using pip by running the following command:

        pip install pre-commit

    Note: If you encounter permission issues, you may need to use sudo or run the command in an elevated terminal.

    3. Verify that pre-commit was installed successfully by running:

        pre-commit --version

    This should display the installed version of pre-commit.


3. Configuration

    Once pre-commit is installed, you need to configure it for your project. The configuration is typically stored in a file named .pre-commit-config.yaml at the root of your project's repository.

    1. Create a .pre-commit-config.yaml file in the root of your repository.
    2. Open the file in a text editor and define your hooks. Hooks are scripts or commands that pre-commit runs on your files. You can find a list of available hooks in the pre-commit repository.

     repos:
        - repo: https://github.com/pre-commit/pre-commit-hooks
            rev: v4.4.0
            hooks:
            - id: trailing-whitespace
            - id: check-yaml
            - id: end-of-file-fixer

        - repo: https://github.com/psf/black
            rev: 23.3.0
            hooks:
            - id: black

        - repo: https://github.com/PyCQA/isort
            rev: 5.12.0
            hooks:
            - id: isort

    3. Save the .pre-commit-config.yaml file.


4. Usage

    With pre-commit configured, you can now run it to check your files before each commit.

    1. Open a terminal or command prompt in the root of your project's repository.

    2. Run the following command:

        pre-commit run --all-files

    This will run all the configured hooks on your files. Any issues or violations will be displayed in the terminal.

    3. Address the issues reported by the hooks. You may need to manually fix the problems or use specific commands provided by the hooks.

    4. Once you've resolved the issues, run the pre-commit run --all-files command again to ensure all the hooks pass successfully.

    5. Finally, you can now commit your changes using your regular Git workflow. The pre-commit hooks will automatically run before each commit to ensure the code meets the defined standards.
