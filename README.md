Ansible Role: Vim and Config
=========

This role sets up vim and my personal vim configuration.

Requirements
------------

Installed versions of:

- vim
- git

Role Variables
--------------

This role installs the vim config for every user defined in vars/*.yml.
Every yaml-file contains a list of users and other related information. The default user is `root` only:

```bash
users:
  - user_dir: /root
    user_group: root
    user_name: root
  - user_dir: /home/<user>
    user_group: <user_group>
    user_name: <user_name>

```

Every yml files belongs to a specific distro version and contains to packages (git and vim) to be installed.
But there is also the possibility to install additional packages by extending the following list:

```bash
  packages:
    - name: git
      description: git client necessary for multiple tasks
    - name: vim
      description: "Vi IMproved" editor

```

Dependencies
------------

none

Example Playbook
----------------

This is a very minimalistic playbook using this role:

```text
- hosts: localhost
  roles:
    - ar-vim-setup
```

License
-------

MIT

Author Information
------------------

Thorsten Winkler
