# Setting up a dev container for Rust

* Primary author: [Michelle Jon](https://github.com/meijoo)

Welcome! In this tutorial, you'll learn how to create a new dev container for Rust. By the end of this guide, you'll set up a Rust development container (dev container) in Visual Studio Code (VS Code).

# Prerequisites

Make sure to have the following:

* [GitHub account](https://github.com/)
* [Git installed](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)
* [Visual Studio Code (VS Code)](https://code.visualstudio.com/)
* [Docker installed](https://www.docker.com/products/docker-desktop)
* Command-line basics

# Creating the Repository: Create a Local Directory and Initialize Git

Open your terminal or command prompt.

Create a new directory for your project.

```
mkdir <name of your repository>
cd <name of your repository>
```
Initialize a new Git repository:

```
git init
```

# Add Development Container Configuration

In VS Code, open the directory. You can do this via: File > Open Folder.

Install the Dev Containers extension for VS Code.

Create a .devcontainer directory in the root of your project. 
Create a file devcontainer.json inside of the "hidden" configuration directory .devcontainer

```
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

# Start your environment

Open your directory where you configured your Dev Container in VS Code.

Install the Dev Containers extension in VS Code.

Reopen the project in the container by pressing Ctrl+Shift+P (or Cmd+Shift+P on Mac).

Type in "Dev Containers: Reopen in Container," and select the option. This may take a few minutes while the image is downloaded and the requirements are installed.
