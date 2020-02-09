Role Name
=========

flatpak

[![Build Status](https://travis-ci.org/cmihai-ansible/flatpak.svg?branch=master)](https://travis-ci.org/cmihai-ansible/flatpak)

Ansible galaxy:
---------------

[https://galaxy.ansible.com/devopstoolbox.flatpak](https://galaxy.ansible.com/devopstoolbox.flatpak)

```bash
ansible-galaxy install devopstoolbox.flatpak
```

Requirements
------------

- For RHEL, a Red Hat subscription or functional local repository.

Role Variables
--------------

```yaml
# Flatpak method: user or system
flatpak_method: system

# Flatpacks repos
flatpak_repos:
  - https://dl.flathub.org/repo/flathub.flatpakrepo

# Packages to install
flatpak_packages:
  - io.neovim.nvim
  - org.gnu.emacs
  - com.visualstudio.code
  - com.slack.Slack
  - com.wps.Office
  - com.skype.Client
  - com.spotify.Client
  - com.obsproject.Studio
  - net.xmind.ZEN
```

Dependencies
------------

- For Red Hat, subscription-manager.

Example Playbook
----------------

```yaml
---
- name: Install flatpak on localhost
  hosts:
    - localhost
  connection: local

  tasks:
    - name: flatpak is configured
      import_role:
        name: devopstoolbox.flatpak
      vars:
        # Flatpak method: user or system
        flatpak_method: system

        # Flatpacks repos
        flatpak_repos:
          - https://dl.flathub.org/repo/flathub.flatpakrepo

        # Packages to install
        flatpak_packages:
          - io.neovim.nvim
          - org.gnu.emacs
          - com.visualstudio.code
          - com.slack.Slack
          - com.wps.Office
          - com.skype.Client
          - com.spotify.Client
          - com.obsproject.Studio
          - net.xmind.ZEN
      tags: flatpak
```

License
-------

MIT

Author Information
------------------

- [Mihai Criveti](https://www.linkedin.com/in/devopstoolbox.)
