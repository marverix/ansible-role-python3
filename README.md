# Ansible Role: Python3

[![Build Status](https://travis-ci.com/marverix/ansible-role-python3.svg?branch=master)](https://travis-ci.com/marverix/ansible-role-python3)
![Ansible Quality Score](https://img.shields.io/ansible/quality/47511)
![Ansible Role](https://img.shields.io/ansible/role/47511)
[![License: ISC](https://img.shields.io/badge/License-ISC-blue.svg)](LICENSE)

Ansible role that installs on linux Python3.

## Features

- ✔️ Installing Python3
  - Select which version
  - Possibility to build from the source
  - Possibility to link as default `python3` executable
- ✔️ Tested with Molecule Verify

## Supported Platforms

- ✔️ Ubuntu 16.04 (Xenial)
- ✔️ Ubuntu 18.04 (Bionic)
- ✔️ Ubuntu 20.04 (Focal)
- ✔️ CentOS 7
- ✔️ CentOS 8

## Requirements

None

## Source repo matrix

| Python | **3.6** | **3.7** | **3.8** |
|-|-|-|-|-|
| **Ubuntu 16** | deadsnakes | deadsnakes | deadsnakes |
| **Ubuntu 18** | official | deadsnakes | deadsnakes |
| **Ubuntu 20** | deadsnakes | deadsnakes | official |
| **CentOS 7** | official | only from source | only from source |
| **CentOS 8** | official | only from source | official |

## Role Variables

Variable | Description | Default Value
--- | --- | ---
`python3_version` | Version of Python to be installed | `3.6`
`python3_only_from_source` | Should build and install only from the source? | `no`
`python3_link` | Link installed version of Python to `/usr/bin/python3` | `no`
`python3_pip_link` | Link installed version of pip to `/usr/bin/pip3` | `no`
`python3_pip_version` | Version of pip to be installed | `20.3.4`

## Dependencies

None

## Example Playbook

1. The simplest one

    ```yml
    ---
    - hosts: all
      roles:
        - marverix.python3

    ```

1. Install Python 3.7

    ```yml
    ---
    - hosts: all
      roles:
        - role: marverix.python3
          vars:
            python3_version: '3.7'
    ```

1. Install Python 3.6, but only from source and link as default python3

    ```yml
    ---
    - hosts: all
      roles:
        - role: marverix.python3
          vars:
            python3_version: '3.6'
            python3_only_from_source: yes
            python3_link: yes
            python3_pip_link: yes
    ```

## License

ISC
