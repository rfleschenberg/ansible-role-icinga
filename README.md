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

* https://github.com/thefinn93/ansible-letsencrypt
  `ansible-galaxy` should pull this in for you automatically. This role assumes
  that letsencrypt is used to get an SSL cert for the Icinga host. You still
  need to apply the letsencrypt role explicitly in your playbook.

Example Playbook
----------------

    - hosts: monitoring
      roles:
        - letsencrypt
        - icinga
      vars:
        letsencrypt_email: you@example.org
        letsencrypt_cert_domains:
          - "{{ inventory_hostname }}"
        icinga_users:
          - username: admin1
            password: "{{ admin1_password }}"
          - username: admin2
            password: "{{ admin2_password }}"
        icinga_objects_dir: files/icinga/objects
        icinga_monitoring_private_key: "{{ my_monitoring_private_key }"

License
-------

BSD

Author Information
------------------

René Fleschenberg <rene@fleschenberg.net>
