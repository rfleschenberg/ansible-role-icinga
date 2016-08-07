ansible-role-icinga
===================

Requirements
------------

None.

Role Variables
--------------

`icinga_users`:
list of users to write to the htpasswd file (see below for an example)

`icinga_objects_dir`:
path to a directory contaiing Icinga object files. All files will be copied to
the Icinga objects directory.

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
        icinga_objects_dir: icinga/objects

License
-------

BSD

Author Information
------------------

René Fleschenberg <rene@fleschenberg.net>
