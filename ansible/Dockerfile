FROM python:3.8.0-buster

RUN apt-get update && apt-get install -y vim jq sshpass
WORKDIR /var/ansible

RUN pip install ansible passlib