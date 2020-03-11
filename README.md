Ansible Role: ansible-linters
=========

Setup git pre-commit hooks for yaml and ansible linters.

* ansible-lint
* ansible-review
* yamllint

Requirements
------------

None

Role Variables
--------------

```yaml
ansible_linters_repo_path: path_of_git_repo
```

Dependencies
------------

None

Example Playbook
----------------

Install linter pre-commit hooks into current base directory of a git repo

```yaml
---
- name: Install Ansible and YAML linters
  hosts: localhost
  connection: local
  gather_facts: false
  become: false
  vars:
    ansible_linters_repo_path: "{{ lookup('ENV', 'PWD') }}"

  roles:
    - ansible-linters
```

License
-------

MIT / BSD

Author Information
------------------

This role was created in 2019 by [Tony Kay](https://cloudassembler.com).
