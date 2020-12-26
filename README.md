# K8s Home Lab

This repo sets up a Kubernetes cluster on one or more Rasberry PI 4B SBCs for experimenting with Devops tools.

## Requirements

- One or more Raspberry PI 4B SBCs running Raspbian Lite
- SSH key named pi
- Digital Ocean account and API token in order to provide external access to local K8s cluster using [Inlets](https://github.com/inlets/inlets)
- Time

## Ansible Playbooks

The PI cluster is configured with a collection of Ansible playbooks.

- `ansible-playbook ssh.yml --ask-pass -vv`
- `ansible-playbook initial-setup.yml -vv`
- `ansible-playbook k3s-cluster.yml -vv`


TODO: playbook for base cluster configuration
 - certificate-manager
 - TLS
 
TODO: fix inletsctl digitalocean size option

## K3s Cluster Configuration

- Traefik is enabled by default
