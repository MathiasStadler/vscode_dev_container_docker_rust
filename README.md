# test vscode with dev container

> create a dev-container with rust
> control container with vscode
> move container to raspberry
> control container remote

## enticement

- s. [TEST_ON](./TEST_ON.md)

## install docker on ubuntu

> [tutorial from here}(https://docs.docker.com/engine/install/ubuntu/)
> deinstall all old version

### deinstall all old version of docker

```bash
for pkg in docker.io docker-doc docker-compose podman-docker containerd runc; do sudo apt-get remove $pkg; done

```

### install newest version via download.docker.com

> follow the website
>> step 1. apt update add necessary package:

```bash
sudo apt autoclean && \
sudo apt -y update && \
sudo apt -y install ca-certificates curl gnupg
```

>> step 2. Add Docker’s official GPG key:

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

>> step 3. Use the following command to set up the repository:

```bash
echo \
  "deb [arch="$(dpkg --print-architecture)" signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
  "$(. /etc/os-release && echo "$VERSION_CODENAME")" stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```

## check vscode --version

### version

### installed extension

## start dev container

## move dev-container to raspberry ,test and run
