# Ansible playbooks

### k3s playbook on Raspberry PI

```
docker build -t ansible .
docker run --rm -it -v ${PWD}/:/var/ansible -v ${HOME}/.ssh/pi:/root/.ssh/pi -v ${HOME}/.ssh/pi.pub:/root/.ssh/pi.pub ansible bash
```

## Initial configuration

`ansible-playbook k3s-cluster.yml -vv`

## k3s cluster

`ansible-playbook k3s-cluster.yml -vv`

