# Setting Up A Dev Container For Rust

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

2. Install the Dev Containers extension for VS Code. Be sure the Dev Container Installs the official rust-analyzer VSCode plugin by the Rust Programming Language Group.

3. Create a `.devcontainer` directory in the root of your project. 
    ```
    mkdir .devcontainer
    ```
4. Create a file `devcontainer.json` inside of the configuration directory `.devcontainer`
    ```
    touch .devcontainer/devcontainer.json
    ```
5. Add the code below to the file. Dev container should use a base image from Microsoft.
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

2. Reopen the project in the container by pressing ++ctrl+shift+p++ (or ++cmd+shift+p++ on Mac).

3. Type in `Dev Containers: Reopen in Container` and select the option. This may take a few minutes while the image is downloaded and the requirements are installed.

4. Once your dev container setup completes, close the current terminal tab and open a new terminal pane within VSCode.

5. Try running `rustc --version` to make sure your dev container is running a recent version of rust.

## Create a New Rust Project

1. Use cargo new to create a binary project by running the following command in the terminal:
```
cargo new my_rust_project --vcs none
```
This will create a new folder named my_rust_project without initializing a Git repository that includes folders Cargo.toml and src with the file main.rs inside.

2. To create a basic "Hello, world!" program, add the following content inside main.rs.
```rust
fn main() {
    println!("Hello, world!");
}
```
## Build and Run the Rust Project
1. Navigate to the project folder by running:
```
cd my_rust_project
```

2. Run the build command:
```
cargo build
```
This compiles the code and produces an executable file in the target/debug folder.

3. To run the built file:
```
./target/debug/my_rust_project
```

This will output:
```
Hello, world!
```

### Run the Project Using cargo run
1. Instead of building and running the executable separately, use:

```
cargo run
```
This command builds the project and runs the executable in one step. You’ll see:
```
Hello, world!
```
The difference Between cargo build and cargo run is that cargo build only compiles the code, while cargo run combines the steps. It compiles and executes the program.
