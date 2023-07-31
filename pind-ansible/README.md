---
name: Podman in Docker + Ansible
description: Develop Ansible workloads in a Docker container with Podman
tags: [local, docker, ansible, podman]
icon: https://raw.githubusercontent.com/zjleblanc/coder-templates/master/logos/podman.png
---

# podman in docker + ansible

An Ansible development template for [coder](https://coder.com/).

## Coder Setup

Follow these steps to configure accessing your workspaces locally on any machine.

### Linux/MacOS

1. Open a terminal and run

   ```bash
   curl -L https://coder.com/install.sh | sh
   ```

### Windows

1. Open a `powershell` window and run

   ```powershell
   winget install Coder.Coder
   ```

## Usage

1. Clone this repository

   ```bash
   git clone https://github.com/zjleblanc/coder-templates
   cd coder-templates/pind-ansible
   ```

1. Login to coder

   ```bash
   coder login CODER_URL
   ```

   > Replace coder.example.com with your coder deplyment URL or IP

1. Create a template

   ```bash
   coder templates create ansible
   ```

1. Edit template metadata

   ```bash
   coder templates edit --display-name "Podman in Docker + Ansible" ansible
   coder templates edit --description "Develop Ansible workloads in a Docker container with Podman" ansible
   coder templates edit --icon "https://raw.githubusercontent.com/zjleblanc/coder-templates/master/logos/podman.png" ansible
   ```

1. Create a workspace

   ```bash
   coder create ansible --template ansible
   ```

   Or,
   Go to `https://CODER_URL/workspaces` and click on **Create Workspace** and select **ansible** template.

> Note: Do not forget to change the `CODER_URL` to your coder deployment URL.

## Container Image

- Based on [podman/stable](https://quay.io/podman/stable)
- Ansible and user configuration layers added in [Dockerfile](./build/Dockerfile)