FROM python:3.8.0-buster

RUN apt-get update && apt-get install -y vim jq sshpass curl net-tools \
    && curl -sLS https://dl.get-arkade.dev | sh \
    && curl -sLSf https://inletsctl.inlets.dev | sh \
    && pip install ansible passlib \
    && ark get helm \
    && ark get kubectl \
    && ark get doctl \
    && ark get k3sup

ENV PATH="${PATH}:/root/.arkade/bin/"
WORKDIR /var/ansible
