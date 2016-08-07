ansible-role-icinga
===================

Requirements
------------

None.

Role Variables
--------------

`icinga_users`: list of users to write to the htpasswd file (see below for an example)

Dependencies
------------

None.

Example Playbook
----------------

    - hosts: monitoring
      roles:
        - role: rfleschenberg.icinga
      vars:
        icinga_users:
          - username: root
            password: secret

License
-------

BSD

Author Information
------------------

René Fleschenberg <rene@fleschenberg.net>
