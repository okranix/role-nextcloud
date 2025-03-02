Nextcloud podman setup
=========

With this ansible role you can deploy Nextcloud and MariaDB container in a podman-pod(1) to get a running Nextcloud instance ready to use from the local host. To reach this Nextcloud from a remote location you have two options:

    Use a reverse proxy like NGINX to forward requests to your Nextcloud pod.
    Listen on all interfaces for incoming traffic for the pod.

I strongly recommend option 1.

Requirements
------------

None

Role Variables
--------------

    ---
    # defaults file for nextcloud_podman_setup
    podman_user: ansible

    # MySQL/MariaDB vars
    mysql_password: ToPSeCrEt2021!
    mysql_root_password: ToPSeCrEt2021!
    mysql_host: localhost

    # Vars for MariaDB container
    mariadb_image: docker.io/mariadb:11.4.5

    # Nextcloud vars
    nextcloud_admin_password: VSnfD2021!
    nextcloud_overwriteprotocol: ""
    nextcloud_overwritecliurl: ""
    nextcloud_trusted_domains: ""

    # SMTP vars
    smtp_host: "smtp.example.com"
    smtp_secure: "tls" # ssl to use SSL, or tls to use STARTTLS
    smtp_port: "587" # (25, 465 for SSL, 587 for STARTTLS)
    smtp_authtype: "LOGIN"
    smtp_name: "bob@example.com"
    smtp_password: "MailSecret1!"
    mail_from_address: "no-reply"
    mail_domain: "example.com"

    # Vars for podman-pod(1)
    pod_port: 127.0.0.1:40671:80

    # Vars for Nextcloud container
    nextcloud_image: docker.io/nextcloud:production-apache
    nextcloud_container_name: nextcloud

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
