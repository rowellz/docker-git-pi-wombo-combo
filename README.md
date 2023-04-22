# Raspberry Pi Docker, Docker Compose, and Git Installer

This Bash script automates the installation of Docker, Docker Compose, and Git on a Raspberry Pi running Raspberry Pi OS.

## Prerequisites

- Raspberry Pi running Raspberry Pi OS
- Internet connection

## Usage

1. Create a new file named `install_docker_compose_git.sh` on your Raspberry Pi.

nano install_docker_compose_git.sh


2. Copy and paste the provided script from [install_docker_compose_git.sh](install_docker_compose_git.sh) into the file.

3. Save and close the file by pressing `Ctrl` + `X`, then `Y`, and finally `Enter` to confirm.

4. Make the script executable:

chmod +x install_docker_compose_git.sh


5. Run the script:

./install_docker_compose_git.sh


The script will update the package lists, upgrade existing packages, and install Docker, Docker Compose, and Git on your Raspberry Pi. It will also add the current user to the Docker group (optional) and enable and start the Docker service.

Once the script completes, you can verify the installation by checking the installed versions:

docker --version
docker-compose --version
git --version


## Components

- **Docker**: A platform for developing, shipping, and running applications in containers.
- **Docker Compose**: A tool for defining and running multi-container Docker applications.
- **Git**: A distributed version control system for tracking changes in source code during software development.

