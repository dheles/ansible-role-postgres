Ansible Role: PostgreSQL
=========

Installs and configures PostgreSQL database server

So far, ~~pretty~~ very minimal.

Requirements
------------

none

Role Variables
--------------
    postgres_debugging:         "{{ debugging | default(false) }}"
    postgres_data_directory:    "/var/lib/pgsql/data"
    postgres_admin_user:        "{{ db_admin_user   | default('postgres') }}"
    postgres_create_users:      "{{ db_create_users | default(false) }}"
    postgres_users:             "{{ db_users        | default(default_db_users) }}"
    default_db_users:
      - user:                   "example_user"
        pass:                   "don't_really_use_this"
        db:                     "you_can_omit_db"
        flags:                  "CREATEDB,NOSUPERUSER"

    postgres_create_databases:  "{{ db_create_databases | default(false) }}"
    postgres_databases:         "{{ db_databases        | default(default_databases) }}"
    default_databases:
      - name:                   "example_db"
        encoding:               "UTF-8"
        owner:                  "example_user"

    postgres_hba_entries:
      - type:                   "local"
        database:               "all"
        user:                   "all"
        address:                ""
        method:                 "md5"

    postgres_listen_addresses:  "localhost"

Dependencies
------------

none

Example Playbook
----------------
NOTE: this role must be run with `become: true`

    - hosts: db
      roles:
      - { role: postgres, tags: ['postgres'], become: true }

License
-------

CC0

Author Information
------------------

Drew Heles
