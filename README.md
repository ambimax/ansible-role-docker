# Ansible Role: Install docker

[![Build Status](https://travis-ci.org/tschifftner/ansible-role-docker.svg?branch=master)](https://travis-ci.org/tschifftner/ansible-role-docker)

Installs docker on Debian/Ubuntu linux servers.

## Requirements

None

## Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml`):

```
docker_install: false

docker_dependencies:
  - apt-transport-https
  - ca-certificates

docker_apt_package: 'docker-engine'

docker_gpg_keyserver: 'hkp://p80.pool.sks-keyservers.net:80'
docker_gpg_id: '58118E89F3A912897C070ADBF76221572C52609D'

docker_repository_url: 'deb https://apt.dockerproject.org/repo debian-{{ ansible_distribution_release|lower }} main'
```

## Dependencies

None.

## Installation

```
$ ansible-galaxy install tschifftner.docker
```

## Example Playbook

    - hosts: server
    
      vars:
        docker_install: true

      roles:
        - { role: tschifftner.docker }

### Install docker compose

```
docker_compose_install: true
docker_compose_version: '1.8.0-rc2'
```

### Install docker machine

```
docker_machine_install: true
docker_machine_version: 'v0.8.0-rc2'
```

## Supported OS

 - Debian 9 (Stretch)
 - Debian 8 (Jessie)
 - Ubuntu 18.04 (Bionic Beaver)
 - Ubuntu 16.04 (Xenial Xerus)
 
## Required ansible version

Ansible 2.5+

## License

[MIT License](http://choosealicense.com/licenses/mit/)

## Author Information

 - [Tobias Schifftner](https://twitter.com/tschifftner), [ambimax® GmbH](https://www.ambimax.de)