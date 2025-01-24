# Setting up a dev container for Rust

* Primary author: [Michelle Jon](https://github.com/meijoo)

Welcome! In this tutorial, you'll learn how to create a new dev container for Rust. By the end of this guide, you'll set up a Rust development container (dev container) in Visual Studio Code (VS Code).

## Prerequisites

Make sure to have the following:

* [GitHub account](https://github.com/)
* [Git installed](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)
* [Visual Studio Code (VS Code)](https://code.visualstudio.com/)
* [Docker installed](https://www.docker.com/products/docker-desktop)

## Creating the Repository: Create a Local Directory and Initialize Git

1. Open your terminal or command prompt.

2. Create a new directory for your project.
    ```
    mkdir <name of your repository>
    cd <name of your repository>
    ```
3. Initialize a new Git repository:
    ```
    git init
    ```

## Add Development Container Configuration

1. In VS Code, open the directory. You can do this via: File > Open Folder.

2. Install the Dev Containers extension for VS Code.

3. Create a `.devcontainer` directory in the root of your project. 
    ```
    mkdir .devcontainer
    ```
4. Create a file `devcontainer.json` inside of the configuration directory `.devcontainer`
    ```
    touch .devcontainer/devcontainer.json
    ```
5. Add the code below to the file
    ```json 
    {
        "name": "Rust Development Environment",
        "image": "mcr.microsoft.com/devcontainers/rust:latest",
        "customizations": {
            "vscode": {
                "extensions": [
                    "rust-lang.rust-analyzer"
                ]
            }
        }
    }
    ```

## Start your environment

1. Open your directory where you configured your Dev Container in VS Code.

2. Install the Dev Containers extension in VS Code.

3. Reopen the project in the container by pressing ++ctrl+shift+p++ (or ++cmd+shift+p++ on Mac).

4. Type in `Dev Containers: Reopen in Container` and select the option. This may take a few minutes while the image is downloaded and the requirements are installed.
