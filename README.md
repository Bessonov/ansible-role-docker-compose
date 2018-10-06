Ansible role for installation or update docker-compose
======================================================

[![Project is](https://img.shields.io/badge/Project%20is-fantastic-ff69b4.svg)](https://github.com/Bessonov/ansible-role-docker-compose)
[![Build Status](https://travis-ci.org/Bessonov/ansible-role-docker-compose.svg?branch=master)](https://travis-ci.org/Bessonov/ansible-role-docker-compose)
[![License](http://img.shields.io/:license-MIT-blue.svg)](https://raw.githubusercontent.com/Bessonov/ansible-role-docker-compose/master/LICENSE.txt)


This role:
- Install docker-compose from docker github releses

Requirements
------------

Requires docker. See also [ansible docker role](https://galaxy.ansible.com/Bessonov/docker/).

Role Variables
--------------

(required) `docker_compose_version` specifies docker-compose version. Allow the keyword `latest` which queries docker-compose Github repo for latest release version.

(optional) `docker_compose_bin` specifies installation path. Defaults to `/usr/local/bin/docker-compose`.

(optional) `docker_compose_as_root` use sudo to install docker-compose. Defaults to `yes`

Dependencies
------------

No special dependencies.

Example Playbook
----------------

Install role globally with:

    ansible-galaxy install Bessonov.docker-compose

or locally:

    ansible-galaxy install --roles-path roles Bessonov.docker-compose

Playbook:

    - hosts: servers
      roles:
         - Bessonov.docker-compose

or with parameter (note the `role` key):

    - hosts: servers
      roles:
         - role: Bessonov.docker-compose
           # required: desired docker-compose version or 'latest'
           docker_compose_version: 1.16.0
           # optional: executable path
           docker_compose_bin: /usr/local/bin/docker-compose
           # optional: should be installed as root
           docker_compose_as_root: yes

License
-------

The MIT License (MIT)

Copyright (c) 2016, Anton Bessonov

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.
