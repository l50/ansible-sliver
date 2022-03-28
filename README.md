# Ansible Role: Sliver

[![Pre-Commit](https://github.com/l50/ansible-sliver/actions/workflows/pre-commit.yaml/badge.svg)](https://github.com/l50/ansible-sliver/actions/workflows/pre-commit.yaml)
[![Molecule Test](https://github.com/l50/ansible-sliver/actions/workflows/molecule.yaml/badge.svg)](https://github.com/l50/ansible-sliver/actions/workflows/molecule.yaml)
[![Ansible Galaxy](https://img.shields.io/badge/Galaxy-sliver-660198.svg?style=flat)](https://galaxy.ansible.com/l50/sliver)

This role installs [Sliver](https://github.com/BishopFox/sliver.git)
on Linux hosts.

## Requirements

N/A

## Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml`):

URL of the sliver install script.

```yaml
install_script_url: https://sliver.sh/install
```

The location where the sliver install script will be downloaded.

```yaml
download_path: /tmp/install.sh
```

## Dependencies

None.

## Example Playbook

```yaml
- hosts: all
  become: yes
  roles:
    - role: l50.sliver
```

## Local Development

Make sure to run the following to develop locally:

```bash
PATH_TO_ROLE="${PWD}"
ln -s "${PATH_TO_ROLE}" "${HOME}/.ansible/roles/l50.sliver"
```

## Testing

To test that the role is working, run the following commands:

```bash
molecule create
molecule converge
# If everything passed, tear down the docker container spawned by molecule:
molecule destroy
```
