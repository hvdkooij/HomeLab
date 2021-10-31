Role Name
=========

Update a debian/ubuntu system with all packages.

Requirements
------------

This role depends on:
 - ansible.builtin.apt

Role Variables
--------------

This role requires no variables.

Dependencies
------------

This role does not depend on roles outside ansible-core.

Example Playbook
----------------

Use it like this:
    - hosts: raspberries
      roles:
        raspberry_update

License
-------

BSD

Author Information
------------------

This is an experimental role created by Hugo van der Kooij <hugo@vanderkooij.org>

Note: It will NOT do a major upgrade!
