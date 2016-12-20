Ansible Role: PostgreSQL
=========

Installs and configures PostgreSQL database server

So far, ~~pretty~~ very minimal.

Requirements
------------

none

Role Variables
--------------

    postgres_data_directory

valid default set for RedHat OS family

Dependencies
------------

none

Example Playbook
----------------

    - hosts: db
      roles:
         - { role: postgres }

License
-------

CC0

Author Information
------------------

Drew Heles
