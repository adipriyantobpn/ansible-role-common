Ansible Role: Common
=========

An Ansible Role that provides common tasks for preparing RHEL/CentOS 7 servers

Requirements
------------

This role needs no special requirements.

Role Variables
--------------

Available variables are listed below, along with default values (see `defaults/main.yml`):

    disable_firewall: False
    disable_selinux: False
    git_username: "{{ ansible_user_id }}"
    git_email: "{{ ansible_user_id }}@{{ ansible_hostname }}"

Dependencies
------------

As EPEL and REMI repository is commonly used by many RHEL/CentOS, this role requires :
  - [geerlingguy.repo-epel](https://galaxy.ansible.com/geerlingguy/repo-epel/)
  - [geerlingguy.repo-remi](https://galaxy.ansible.com/geerlingguy/repo-remi/)

Those required roles maintain their own role variables. Please read their documentations for more detailed explanations of how to use and supported role variables.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - name: Prepare CentOS 7 server
      hosts:  centos7
      roles:
        - role: adipriyantobpn.common
          disable_firewall: True
          disable_selinux: True
          git_username: "Adi Priyanto"
          git_email: "adipriyanto.bpn@gmail.com"


License
-------

BSD

Author Information
------------------

This role was created in 2017 by [Adi Priyanto](https://github.com/adipriyantobpn) as a learning purpose for community.
