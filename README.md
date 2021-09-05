# K8s Home Lab

Set up a Kubernetes cluster running k3s on one or more Rasberry PI 4Bs.

## Requirements

- One or more Raspberry PI 4Bs (4GB+ preferred) running Raspbian Lite
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


# Ansible playbooks

### k3s playbook on Raspberry PI

```
docker build -t homelab .
docker run --rm -it \
  -v ${PWD}/:/var/ansible \
  -v ${HOME}/.ssh/pi:/root/.ssh/pi \
  -v ${HOME}/.ssh/pi.pub:/root/.ssh/pi.pub \
  homelab bash
```

## Initial configuration

`ansible-playbook plays/ssh.yml -vvv`
`ansible-playbook plays/initial-setup.yml -vvv`

## k3s cluster

`ansible-playbook plays/k3s-cluster.yml -vv`

Add a new node to an existing cluster.

`ansible-playbook -i <ip>, plays/k3s-add-node.yml -vv -e "new_hostname=node-X"`
