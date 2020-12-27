# K8s Home Lab

Set up a Kubernetes cluster running k3s on one or more Rasberry PI 4B SBCs.

## Requirements

- One or more Raspberry PI 4B SBCs (4GB preferred) running Raspbian Lite
- Linode account and API token in order to provide external access to local K8s cluster using [Inlets](https://github.com/inlets/inlets)

## Ansible Playbooks

The PI cluster is configured with a collection of Ansible playbooks.

- `ansible-playbook ssh.yml --ask-pass -vv`
- `ansible-playbook initial-setup.yml -vv`
- `ansible-playbook k3s-cluster.yml -vv`
- `ansible-playbook k3s-cluster.yml --tags "fetch-kubeconfig" -vv`


TODO: playbook for base cluster configuration
 - certificate-manager
 - docker-registry
 - TLS for registry
 - kubernetes-dashboard
 - JenkinsX or Tekton

TODO: exit-server playbook with TLS and domain

TODO: Sample app with Helm chart and pipeline 
 
