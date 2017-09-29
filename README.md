# ansible-macos-npm
Ansible role to manage macOS npm installs.

[![Build Status](https://img.shields.io/travis/feffi/ansible-macos-npm.svg)](https://travis-ci.org/feffi/ansible-macos-npm) [![Github All Releases](https://img.shields.io/github/downloads/feffi/ansible-macos-npm/total.svg)](https://github.com/feffi/ansible-macos-npm) [![GitHub forks](https://img.shields.io/github/forks/feffi/ansible-macos-npm.svg?style=social&label=Fork)](https://github.com/feffi/ansible-macos-npm) [![GitHub stars](https://img.shields.io/github/stars/feffi/ansible-macos-npm.svg?style=social&label=Star)](https://github.com/feffi/ansible-macos-npm) [![GitHub watchers](https://img.shields.io/github/watchers/feffi/ansible-macos-npm.svg?style=social&label=Watch)](https://github.com/feffi/ansible-macos-npm) [![Twitter Follow](https://img.shields.io/twitter/follow/feffi1.svg?style=social&label=Follow)](https://twitter.com/feffi1) [![License](http://img.shields.io/:license-mit-blue.svg)](https://github.com/feffi/ansible-macos-npm/blob/master/LICENSE)

## Requirements
- Ansible 2.3

### ansible.cfg
```
hash_behaviour = merge
```

## Install
Just add the role to your ``requirements.yml`` file:
```yaml
- src: https://github.com/feffi/ansible-macos-npm.git
  name: feffi.macos-npm
```

## Role Variables
All role based variables are listed below, along with default values:

```yaml
macos_npm:
  # Packages to install via npm
  packages: []
```

## Dependencies
None.

## Example Playbook

```yaml
    - hosts: all
      vars:
        macos_npm:
          packages: [
            { name: "vtop", global: true }
          ]
      roles:
        - { role: feffi.macos-npm }
```
Or with local parameters:

```yaml
    - hosts: all
      roles:
        - { role: feffi.macos-npm,
            macos_npm: {
              packages: [
                { name: "vtop", global: true }
              ]
            }
          }
```
