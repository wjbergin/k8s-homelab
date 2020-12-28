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

`ansible-playbook -i <ip>, plays/k3s-add-node.yml -vv --extra-vars="new_hostname=node-X"`

