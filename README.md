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

>> step 4. Update the apt package index:

```bash
sudo apt-get update
```

>> step 5. Install latest docker engine

```bash
sudo apt-get install -y docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```

>> step 6. Verify that the Docker Engine installation is successful by running the hello-world image

```bash
sudo docker run hello-world
```

>> step 7. Check of error via return code - should zero

```bash
echo $?
```

>> DOCKER on os installed :-)

## check vscode --version

### version

```bash
code --version
1.81.0
6445d93c81ebe42c4cbd7a60712e0b17d9463e97
x64
```

### installed extension with version

```bash
code --list-extensions  --show-versions
```

## start dev container

## move dev-container to raspberry ,test and run
