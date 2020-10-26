Role Name
=========

This role automates the request of a Letsencrypt SSL Certificate for an Apache2 server.

Requirements
------------

This role supports:
- Ubuntu 20.04

Required steps:
1. Register the (sub)domain; 
2. Ensure port 80 and 443 are open on the server (configure HAProxy for TCP ports);
3. Add the role to the playbook;
4. Override the defaults in the playbook;

Role Variables
--------------

See defaults/main.yml for more information.

Dependencies
------------

See defaults/main.yml for more information.

Example Playbook
----------------

For adding additional domain controller use the example below

    - hosts: server
      become: yes

      vars:
        #-- Custom settings: role-certbot-apache2 --
        certbot_servername   : 'example.com'
        certbot_serveralias  : 'test.example.com'
        certbot_serveradmin  : 'support@example.com'
        certbot_documentroot : '/var/www/html'
        
      roles:
        - role-samba4

License
-------

GPLv3

Author Information
------------------

I: https://www.bitfinity.nl
E: info@bitfinity.nl

