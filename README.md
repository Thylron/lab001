# Ansible setup scripts for Dependency Track on Centos 7.9 with Dockers

## Prerequisite

### Hardware topology

- One Ansible manager server (srv-ansible-node-manager)
- One Dependency Track server (srv-dependencytrack)

### Users

- ansible-manager on Ansible manager server
- ansible-user on Dependency Track server

### SSH connexion commands

- [ansible-manager@srv-ansible-node-manager ~]$ ssh-keygen -t rsa
- [ansible-manager@srv-ansible-node-manager ~]$ ssh-copy-id ansible-user@srv-dependencytrack

### Sudo configuration

[root@srv-dependencytrack ~]# usermod -a -G wheel ansible-user

## Ansible commands

### Systems tasks

ansible-playbook -i inventaire.ini --user ansible-user --become --ask-become-pass system-tasks.yml

### Install Docker

ansible-playbook -i inventaire.ini --user ansible-user --become --ask-become-pass docker-installation.yml

