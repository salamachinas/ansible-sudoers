ansible-sudoers
===============

This role manage sudoers

[![Ansible Galaxy](https://img.shields.io/ansible/role/xxxxx.svg)](https://galaxy.ansible.com/salamachinas/sudoers/)

Requirements
------------

This role requires Ansible 2.0 or higher and platform requirements are listed
in the metadata file.

Install
-------

```sh
ansible-galaxy install salamachinas.sudoers
```

Example Playbook
----------------

```yaml
- name: provision servers
  hosts: all
  become: true
  roles:
    - { role: 'salamachinas.sudoers', tags: 'sudoers' }
  vars:
    promoted:
      - {name: ansible, promote: ALL, nopasswd: true}
      - {name: example, promote: app, nopasswd: false}
```

Tests
-----

```sh
docker build -t test-ansible-sudoers-centos7 -f tests/Dockerfile_centos7 --force-rm .
docker build -t test-ansible-sudoers-debian7 -f tests/Dockerfile_debian7 --force-rm .
docker build -t test-ansible-sudoers-debian8 -f tests/Dockerfile_debian8 --force-rm .
docker build -t test-ansible-sudoers-ubuntu14 -f tests/Dockerfile_ubuntu14 --force-rm .
docker build -t test-ansible-sudoers-ubuntu16 -f tests/Dockerfile_ubuntu16 --force-rm .
```
