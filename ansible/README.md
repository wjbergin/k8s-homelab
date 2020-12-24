# Ansible playbooks

### k3s playbook on Raspberry PI

```
docker build -t ansible .
docker run --rm -it -v ${PWD}/:/var/ansible -v ${HOME}/.ssh/pi.pub:/root/pi.pub ansible bash
```

`ansible-playbook k3s-on-pi.yml --ask-pass -vvv`

