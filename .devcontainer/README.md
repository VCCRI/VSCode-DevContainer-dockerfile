# Development Container

This project uses a development container to provide a consistent development environment. The container is defined using Docker and configured for Visual Studio Code.

## Prerequisites

- [Docker](https://www.docker.com/get-started) installed on your machine
- [Visual Studio Code](https://code.visualstudio.com/) installed on your machine
- [Remote - Containers extension](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers) installed in Visual Studio Code

## Getting Started

1. **Clone the repository**:
    ```sh
    git clone <repository-url>
    cd <repository-directory>
    ```

2. **Open the repository in Visual Studio Code**:
    ```sh
    code .
    ```

3. **Reopen in Container**:
    - Press `F1` to open the command palette.
    - Type `Remote-Containers: Reopen in Container` and select it.

Visual Studio Code will build the Docker image defined in the `.devcontainer` folder and start a container with the specified configuration.

## Configuration Details

- **Dockerfile**: The container is built using the `Dockerfile` located in the `.devcontainer` folder. It uses `ubuntu:20.04` as the base image and installs `curl`, `git`, and `vim`.

- **devcontainer.json**: The configuration file for the development container.
    - **name**: The name of the container.
    - **build**: Specifies the Dockerfile to use for building the container.
    - **customizations**: Custom settings for Visual Studio Code.
        - **settings**: Sets the default shell to `/bin/bash`.
        - **extensions**: Installs the `ms-vscode.cpptools` and `ms-python.python` extensions.
    - **postCreateCommand**: Command to run after the container is created.
    - **workspaceFolder**: The folder to open in the container.
    - **workspaceMount**: Mounts the local workspace folder into the container.

## Post-Create Command

After the container is created, the following command is run:
```sh
echo 'Container setup complete!'