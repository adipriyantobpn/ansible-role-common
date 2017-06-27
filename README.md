Ansible Role: Common
=========

An Ansible Role that provides common tasks for preparing RHEL/CentOS 7 servers

Requirements
------------

This role needs no special requirements, except sudo access to install yum repositories & packages ( plus internet connection, of cource :D ).

Role Variables
--------------

Available variables are listed below, along with default values (see `defaults/main.yml`):

      disable_firewall:           False
      disable_selinux:            False
      git_username:               "{{ ansible_user_id }}"
      git_email:                  "{{ ansible_user_id }}@{{ ansible_hostname }}"
      repo_location:              indonesia
      centos_base_enabled:        yes
      centos_updates_enabled:     yes
      centos_extras_enabled:      yes
      centos_centosplus_enabled:  yes
      centos_cr_enabled:          no
      centos_fasttrack_enabled:   no
      epel_enabled:               yes
      remi_enabled:               no
      remi_safe_enabled:          yes
      remi_php54_enabled:         no
      remi_php55_enabled:         no
      remi_php56_enabled:         no
      remi_php70_enabled:         no
      remi_php71_enabled:         yes
      basic_packages:
        - vim
        - tree

Dependencies
------------

As EPEL and REMI repository is commonly used by many RHEL/CentOS, this role requires :
  - [geerlingguy.repo-epel](https://galaxy.ansible.com/geerlingguy/repo-epel/)
  - [geerlingguy.repo-remi](https://galaxy.ansible.com/geerlingguy/repo-remi/)

Those required roles maintain their own role variables. Please read their documentations for more detailed explanations of how to use and supported role variables.

Example Playbook
----------------

    - name: Prepare CentOS 7 server
      hosts: centos7
      roles:
        - role: adipriyantobpn.common
          git_username:               "Adi Priyanto"
          git_email:                  "adipriyanto.bpn@gmail.com"
          repo_location:              vagrant
          centos_base_enabled:        yes
          centos_updates_enabled:     yes
          centos_extras_enabled:      yes
          centos_centosplus_enabled:  no
          centos_cr_enabled:          no
          centos_fasttrack_enabled:   no
          epel_enabled:               yes
          remi_enabled:               no
          remi_safe_enabled:          yes
          remi_php54_enabled:         no
          remi_php55_enabled:         no
          remi_php56_enabled:         no
          remi_php70_enabled:         yes
          remi_php71_enabled:         no
          basic_packages:
            - yum-plugin-list-data
            - yum-plugin-fs-snapshot
            - yum-plugin-changelog
            - vim
            - tree
            - lynx


License
-------

BSD

Author Information
------------------

This role was created in 2017 by [Adi Priyanto](https://github.com/adipriyantobpn) as a learning purpose for community.
