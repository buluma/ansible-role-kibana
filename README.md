# Ansible role [kibana](https://galaxy.ansible.com/ui/standalone/roles/buluma/kibana/documentation)

Kibana for Linux.

|GitHub|Version|Issues|Pull Requests|Downloads|
|------|-------|------|-------------|---------|
|[![github](https://github.com/buluma/ansible-role-kibana/actions/workflows/molecule.yml/badge.svg)](https://github.com/buluma/ansible-role-kibana/actions/workflows/molecule.yml)|[![Version](https://img.shields.io/github/release/buluma/ansible-role-kibana.svg)](https://github.com/buluma/ansible-role-kibana/releases/)|[![Issues](https://img.shields.io/github/issues/buluma/ansible-role-kibana.svg)](https://github.com/buluma/ansible-role-kibana/issues/)|[![PullRequests](https://img.shields.io/github/issues-pr-closed-raw/buluma/ansible-role-kibana.svg)](https://github.com/buluma/ansible-role-kibana/pulls/)|[![Ansible Role](https://img.shields.io/ansible/role/d/buluma/kibana)](https://galaxy.ansible.com/ui/standalone/roles/buluma/kibana/documentation)|

## [Example Playbook](#example-playbook)

This example is taken from [`molecule/default/converge.yml`](https://github.com/buluma/ansible-role-kibana/blob/master/molecule/default/converge.yml) and is tested on each push, pull request and release.

```yaml
---
- name: Converge
  hosts: all
  become: true
  gather_facts: true

  pre_tasks:
    - name: Update apt cache.
      apt: update_cache=true cache_valid_time=600
      when: ansible_os_family == 'Debian'

  roles:
    - role: buluma.kibana
```

The machine needs to be prepared. In CI this is done using [`molecule/default/prepare.yml`](https://github.com/buluma/ansible-role-kibana/blob/master/molecule/default/prepare.yml):

```yaml
---
- name: Prepare
  hosts: all
  become: true
  gather_facts: false

  roles:
    - role: buluma.bootstrap
    - role: buluma.core_dependencies
    - role: robertdebock.elastic_repo
```

Also see a [full explanation and example](https://buluma.github.io/how-to-use-these-roles.html) on how to use these roles.

## [Role Variables](#role-variables)

The default values for the variables are set in [`defaults/main.yml`](https://github.com/buluma/ansible-role-kibana/blob/master/defaults/main.yml):

```yaml
---
# Elastic offers both "oss" (Apache 2.0 license) and "elastic"
# (Elastic license). Select the type here. Either "oss" or "elastic"
kibana_type: elastic

# The IP addres to bind on.
kibana_server_host: "0.0.0.0"

# The TCP port to bind on.
kibana_server_port: 5601

# A list of elasticsearch urls.
kibana_elasticsearch_hosts:
  - "http://localhost:9200"
```

## [Requirements](#requirements)

- pip packages listed in [requirements.txt](https://github.com/buluma/ansible-role-kibana/blob/master/requirements.txt).

## [State of used roles](#state-of-used-roles)

The following roles are used to prepare a system. You can prepare your system in another way.

| Requirement | GitHub | Version |
|-------------|--------|--------|
|[buluma.elasticsearch](https://galaxy.ansible.com/buluma/elasticsearch)|[![Ansible Molecule](https://github.com/buluma/ansible-role-elasticsearch/actions/workflows/molecule.yml/badge.svg)](https://github.com/buluma/ansible-role-elasticsearch/actions/workflows/molecule.yml)|[![Version](https://img.shields.io/github/release/buluma/ansible-role-elasticsearch.svg)](https://github.com/shadowwalker/ansible-role-elasticsearch)|
|[buluma.bootstrap](https://galaxy.ansible.com/buluma/bootstrap)|[![Ansible Molecule](https://github.com/buluma/ansible-role-bootstrap/actions/workflows/molecule.yml/badge.svg)](https://github.com/buluma/ansible-role-bootstrap/actions/workflows/molecule.yml)|[![Version](https://img.shields.io/github/release/buluma/ansible-role-bootstrap.svg)](https://github.com/shadowwalker/ansible-role-bootstrap)|
|[buluma.core_dependencies](https://galaxy.ansible.com/buluma/core_dependencies)|[![Ansible Molecule](https://github.com/buluma/ansible-role-core_dependencies/actions/workflows/molecule.yml/badge.svg)](https://github.com/buluma/ansible-role-core_dependencies/actions/workflows/molecule.yml)|[![Version](https://img.shields.io/github/release/buluma/ansible-role-core_dependencies.svg)](https://github.com/shadowwalker/ansible-role-core_dependencies)|
|[robertdebock.elastic_repo](https://galaxy.ansible.com/buluma/robertdebock.elastic_repo)|[![Ansible Molecule](https://github.com/buluma/robertdebock.elastic_repo/actions/workflows/molecule.yml/badge.svg)](https://github.com/buluma/robertdebock.elastic_repo/actions/workflows/molecule.yml)|[![Version](https://img.shields.io/github/release/buluma/robertdebock.elastic_repo.svg)](https://github.com/shadowwalker/robertdebock.elastic_repo)|

## [Context](#context)

This role is a part of many compatible roles. Have a look at [the documentation of these roles](https://buluma.github.io/) for further information.

Here is an overview of related roles:

![dependencies](https://raw.githubusercontent.com/buluma/ansible-role-kibana/png/requirements.png "Dependencies")

## [Compatibility](#compatibility)

This role has been tested on these [container images](https://hub.docker.com/u/buluma):

|container|tags|
|---------|----|
|[Debian](https://hub.docker.com/r/buluma/debian)|all|
|[EL](https://hub.docker.com/r/buluma/enterpriselinux)|all|
|[Fedora](https://hub.docker.com/r/buluma/fedora)|all|
|[Ubuntu](https://hub.docker.com/r/buluma/ubuntu)|focal|

The minimum version of Ansible required is 2.12, tests have been done to:

- The previous version.
- The current version.
- The development version.

If you find issues, please register them in [GitHub](https://github.com/buluma/ansible-role-kibana/issues)

## [Changelog](#changelog)

[Role History](https://github.com/buluma/ansible-role-kibana/blob/master/CHANGELOG.md)

## [License](#license)

[Apache-2.0](https://github.com/buluma/ansible-role-kibana/blob/master/LICENSE)

## [Author Information](#author-information)

[Shadow Walker](https://buluma.github.io/)
