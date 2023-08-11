# test vscode with dev container

> create a dev-container with rust
> control container with vscode
> move container to raspberry
> control container remote

## [yt tutorial from here](https://www.youtube.com/watch?v=SDa3v4Quj7Y)

## environment

- s. [TEST_ON](./TEST_ON.md)

## install docker on ubuntu

> [tutorial from here](https://docs.docker.com/engine/install/ubuntu/)

### deinstall all old version of docker

```bash
for pkg in docker.io docker-doc docker-compose podman-docker containerd runc; do sudo apt-get remove $pkg; done
```

### install newest version via download.docker.com

> follow the website
>
> step 1. apt update add necessary package:

```bash
sudo apt autoclean && \
sudo apt -y update && \
sudo apt -y install ca-certificates curl gnupg
```

> step 2. Add Docker’s official GPG key:

```bash
DIR="/etc/apt/keyrings"
if [ -d "$DIR" ]; then
  # Take action if $DIR exists. #
  echo "Take directory if exists ${DIR}..."
else
echo "The directory if NOT exists create ${DIR}..."
sudo install -m 0755 -d /etc/apt/keyrings
fi && \
echo "install key"
FILE="/etc/apt/keyrings/docker.gpg"
if [ -f "$FILE" ]; then
    echo "Key if exists ${FILE}..."
    ls -la /etc/apt/keyrings/docker.gpg
else
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg && \
sudo chmod a+r /etc/apt/keyrings/docker.gpg
ls -la /etc/apt/keyrings/docker.gpg
fi
```

> step 3. Use the following command to set up the repository:

```bash
echo "Update repository - check file exists"
FILE="/etc/apt/sources.list.d/docker.list"
if [ -f "$FILE" ]; then
    echo "File/repo if exists ${FILE}..."
    ls -la /etc/apt/sources.list.d/docker.list
else
echo "File/repo if NOT exists CREATE ${FILE}..."
echo \
  "deb [arch="$(dpkg --print-architecture)" signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
  "$(. /etc/os-release && echo "$VERSION_CODENAME")" stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
fi
```

> step 4. Update the apt package index:

```bash
sudo apt-get update
```

> step 5. Install latest docker engine

```bash
sudo apt-get install -y docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```

> step 6. Verify that the Docker Engine installation is successful by running the hello-world image

```bash
sudo docker run hello-world
```

> step 7. Check of error via return code - should zero

```bash
echo $?
```

> DOCKER on os is installed :-)

## check vscode --version

### version

```bash
code --version
1.81.0
6445d93c81ebe42c4cbd7a60712e0b17d9463e97
x64
```

### list installed extension with version on vscode terminal/cli

```bash
code --list-extensions  --show-versions
```

## run container-dev inside vscode

### install extensions in vscode via cli/bash

```bash
code --install-extension ms-vscode-remote.vscode-remote-extensionpack
```

### stop and start vscode

### check extensions for remote development are installed

```bash
code --list-extensions  --show-versions |grep remote
# you should this
ms-vscode-remote.remote-containers@0.304.0
ms-vscode-remote.remote-ssh@0.102.0
ms-vscode-remote.remote-ssh-edit@0.86.0
ms-vscode-remote.remote-wsl@0.81.0
ms-vscode-remote.vscode-remote-extensionpack@0.24.0
ms-vscode.remote-explorer@0.4.1
ms-vscode.remote-server@1.4.0
```

### Hit: Small [VSCode development Docker container for Rust](https://www.reddit.com/r/rust/comments/ohj69c/vscode_development_docker_container_for_rust/)

- [short cut dev container](https://github.com/kherge/sh.dev)

### you start a dev container explained in the yt video too

1. press [strg]+[shift]+[p]
2. search for => DevContainers: Clone Repository in Container Volume...
3. select => Clone a repository from GitHub in a Container Volume ...
4. select => Clone a repository from GitHub in a Container Volume
5. select => a sample GitHub repo e.g. MathiasStadler/vscode_dev_container_hello_world_rust
6. select => branch name e.g. master
7. ATTENTION This vscode instance will close and open a new session with your repo in a docker container

> size of directory with container

```bash
 du -hs ./target/
```

### [Dev Containers Tips and Tricks](https://code.visualstudio.com/docs/devcontainers/tips-and-tricks)

#### [install the Resource Monitor extension](https://marketplace.visualstudio.com/items?itemName=mutantdino.resourcemonitor&ssr=false#overview)

```bash
code --install-extension mutantdino.resourcemonitor
```

### open terminal im container

## start dev container

## move dev-container to raspberry ,test and run
