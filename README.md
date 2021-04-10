# Ansible Role: Python3

[![Build Status](https://travis-ci.com/marverix/ansible-role-python3.svg?branch=master)](https://travis-ci.com/marverix/ansible-role-python3)
![Ansible Quality Score](https://img.shields.io/ansible/quality/47511)
![Ansible Role](https://img.shields.io/ansible/role/47511)
[![License: ISC](https://img.shields.io/badge/License-ISC-blue.svg)](LICENSE)

Ansible role that installs on linux Python3.

## Features

- ✔️ Installing Python3
  - For Ubuntu from ppa
  - For CentOS from EPEL
- ✔️ Installing Python3 packages:
  - dev/devel
  - wheel
  - setuptools
  - pip
  - virtualenv
- ✔️ Possibility to install additional pip packages globally
- ✔️ Tested with Molecule Verify

## Supported Platforms

- ✔️ Ubuntu 18.04 (Bionic)
- ✔️ Ubuntu 20.04 (Focal)
- ✔️ CentOS 7
- ✔️ CentOS 8

## Requirements

None

## Role Variables

Variable | Description | Default Value
--- | --- | ---
`python3_pip_version` | Version of pip to be installed | `20.3.4`
`python3_pip_install_globally` | List of `pip` packages that should be installed globally | `[]`
`python3_epel_release_version` | EPEL Release Version (for CentOS only) | `7-13`

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

1. Install globally `black` and `flake8`

    ```yml
    ---
    - hosts: all
      roles:
        - role: marverix.python3
          vars:
            python3_pip_install_globally:
              - black
              - flake8
    ```

## License

ISC
