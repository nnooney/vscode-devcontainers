# vscode-devcontainers

Development Container definitions for use in Visual Studio Code. Inspired by [microsoft/vscode-dev-containers](https://github.com/microsoft/vscode-dev-containers).

## Usage

The [`containers`](containers/) folder holds reusable container defintions. Copy the `.devcontainer` folder from one of the containers definitions to use in your project. Then open the project using VSCode's Remote Containers extension.

## How it works

### What [microsoft/vscode-dev-containers](https://github.com/microsoft/vscode-dev-containers) does

VSCode publishes several container defintiions using the Microsoft Container Registry (images prefixed with `vscode/devcontainers` at https://mcr.microsoft.com/v2/_catalog). The GitHub repository [microsoft/vscode-dev-containers](https://github.com/microsoft/vscode-dev-containers) uses these published images in the `.devcontaioner/Dockerfile` files for each container definition (in the `FROM` expression).

The images published to the Microsoft Container Registry are built from non-Microsoft Docker images using the `base.Dockerfile` files in the aforementioned GitHub repository.

### What this repository does

Rather than rely upon the Microsoft base images, this repository publishes its own set of base Docker images using the GitHub Container Registry. Images are published automatically using GitHub Actions. See the [`base`](base/) folder for the Dockerfile definitions used to build these images.

The container definitions all rely upon the base images published by this repository.
