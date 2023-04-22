# Raspberry Pi Docker, Docker Compose, and Git Installer

This Bash script automates the installation of Docker, Docker Compose, and Git on a Raspberry Pi running Raspberry Pi OS.

## Prerequisites

- Raspberry Pi running Raspberry Pi OS
- Internet connection

## Usage

1. Create a new file named `install_docker_compose_git.sh` on your Raspberry Pi.

`nano install_docker_compose_git.sh`


2. Copy and paste the provided script below into the file.

`#!/bin/bash

# Update package lists and upgrade existing packages
sudo apt-get update && sudo apt-get upgrade -y

# Install required dependencies
sudo apt-get install -y apt-transport-https ca-certificates curl software-properties-common

# Install Git
sudo apt-get install -y git

# Add Docker's official GPG key
curl -fsSL https://download.docker.com/linux/raspbian/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg

# Add Docker's official repository to sources.list
echo "deb [arch=armhf signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/raspbian $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

# Update package lists to include Docker packages
sudo apt-get update

# Install Docker
sudo apt-get install -y docker-ce

# Add current user to Docker group (optional)
sudo usermod -aG docker $USER

# Enable and start Docker service
sudo systemctl enable docker
sudo systemctl start docker

# Install Docker Compose
sudo apt-get install -y python3-pip libffi-dev libssl-dev
sudo pip3 install docker-compose

# Print Docker and Docker Compose versions
echo "Docker version:"
docker --version
echo "Docker Compose version:"
docker-compose --version

echo "Installation complete!"
`

3. Save and close the file by pressing `Ctrl` + `X`, then `Y`, and finally `Enter` to confirm.

4. Make the script executable:

`chmod +x install_docker_compose_git.sh`


5. Run the script:

`./install_docker_compose_git.sh`


The script will update the package lists, upgrade existing packages, and install Docker, Docker Compose, and Git on your Raspberry Pi. It will also add the current user to the Docker group (optional) and enable and start the Docker service.

Once the script completes, you can verify the installation by checking the installed versions:

docker --version
docker-compose --version
git --version


## Components

- **Docker**: A platform for developing, shipping, and running applications in containers.
- **Docker Compose**: A tool for defining and running multi-container Docker applications.
- **Git**: A distributed version control system for tracking changes in source code during software development.

