---
name: Podman in Docker + Ansible
description: Develop Ansible workloads in a Docker container with Podman
tags: [local, docker, ansible, podman]
icon: https://d4.alternativeto.net/9Eu71ciQNFhgLmHwvpo9uY7poyHbWgoqSdeA5a1-JsY/rs:fit:1200:1200:0/g:ce:0:0/YWJzOi8vZGlzdC9zL3BvZG1hbl81MTAyNjlfZnVsbC5wbmc.jpg
---

# podman in docker + ansible

To get started, run `coder templates init`. When prompted, select this template.
Follow the on-screen instructions to proceed.

## Editing the image

Edit the `Dockerfile` and run `coder templates push` to update workspaces.

## code-server

`code-server` is installed via the `startup_script` argument in the `coder_agent`
resource block. The `coder_app` resource is defined to access `code-server` through
the dashboard UI over `localhost:13337`.

## Extending this template

See the [kreuzwerker/docker](https://registry.terraform.io/providers/kreuzwerker/docker) Terraform provider documentation to
add the following features to your Coder template:

- SSH/TCP docker host
- Registry authentication
- Build args
- Volume mounts
- Custom container spec
- More

We also welcome contributions!
