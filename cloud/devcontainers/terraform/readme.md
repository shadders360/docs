# example dev containers

vscode has integrated (devcontainers)[https://github.com/devcontainers] operations. This is different from the Docker desktop devcontainers

currently I perform

1. git clone from our private BB server
2. mount file system into vscode container. (speed has improved from old mac)

Unable to clone into a Docker volume ie when cloning from GitHub. May need to create a image to do this but will work with docker
bind of local to see how thing perform

These dev containers are for azure using terraform

## cloud/devcontainers/terraform/devcontainer-0.0.1.json

This is the original version used on intel mac, version 0.0.2 has been improved due to the devcontainer spec

## cloud/devcontainers/terraform/devcontainer-0.0.2.json

This is the 2023 version for the new M2 mac. Features appear to simplified the process. (to investigate)

## cloud/devcontainers/terraform/devcontainer-simple-0.0.1.json

This pulls a prebuilt image using the devcontaner CLI [see](https://github.com/devcontainers/cli)

Docker file cloud/devcontainers/terraform/Dockerfile.simple was used in this devcontainer.