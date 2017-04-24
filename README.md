ansible-role-icinga
===================

Requirements
------------

* Debian Jessie (other platforms may work, but are untested)

Role Variables
--------------

`icinga_users`:
List of users to write to the htpasswd file (see below for an example)

`icinga_objects_dir`:
Path to a directory containng Icinga object files. All files will be copied to
the Icinga objects directory.

`icinga_monitoring_private_key`:
Private SSH key for the Icinga user (`nagios`). The idea is that Icinga can use
this key to log into monitored systems.


Dependencies
------------

None.

Example Playbook
----------------

    - hosts: monitoring
      roles:
        - icinga

License
-------

BSD

Author Information
------------------

René Fleschenberg <rene@fleschenberg.net>
