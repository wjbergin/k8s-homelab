# K8s Home Lab

This repo sets up a Kubernetes cluster using one or more Rasberry PI 4B SBCs for experimenting with Devops tools.

## Requirements

- One or more Raspberry PI 4B SBCs running Raspbian Lite
- ssh key named pi
- Digital Ocean account and API token in order to provide external access to local K8s cluster using [Inlets](https://github.com/inlets/inlets)
- Time

## Ansible Playbooks

After flashing the SD cards with Raspbian Lite, the cluster of PIs is configured with a collection of Ansible playbooks.
