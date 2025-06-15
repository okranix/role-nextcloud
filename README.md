Nextcloud docker setup
=========

With this ansible role you can deploy Nextcloud as docker container
This Role was designed and tested for raspberry pi os.

Requirements
------------

Role Variables
--------------

    ---
    apt_repo_uris: https://download.docker.com/linux/debian
    apt_repo_suites: stable
    apt_repo_components:
    apt_repo_signed_by: /usr/share/keyrings/docker_key.gpg


Dependencies
------------

None

Example Playbook
----------------

    - name: Nextcloud podman setup
      hosts: servers
      roles:
         - role-nextcloud

License
-------

GPL-2.0-or-later
