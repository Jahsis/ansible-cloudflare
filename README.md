Ansible-cloudflare
=========

Install mod_cloudflare for apache or configure NGINX to get real IP when using cloudflare.

## Apache

This role will download, compile and install
[mod_cloudflare](https://github.com/cloudflare/mod_cloudflare.git) for apache
more information on [cloudflare website](https://support.cloudflare.com/hc/en-us/articles/203656534-How-do-I-restore-original-visitor-IP-with-Apache-2-4-)

## Nginx

This role will add configuration file into `/etc/nginx/conf.d/` to ensure all
IP's from cloudflare are set and configured to use real IP more information
on [cloudflare website](https://support.cloudflare.com/hc/en-us/articles/200170706-How-do-I-restore-original-visitor-IP-with-Nginx-)

Requirements
------------

Installed apache2 or nginx

Role Variables
--------------

ansible_cloudflare_server: should be "apache2" or "nginx" depending on which server you have installed on you machine

Dependencies
------------

No dependencies

Example Playbook
----------------

### Apache

    - hosts: servers
      roles:
         - { role: ansible-cloudflare, ansible_cloudflare_server: apache2 }

### Nginx

    - hosts: servers
      roles:
         - { role: ansible-cloudflare, ansible_cloudflare_server: nginx }

License
-------

BSD

Author Information
------------------

Created by [Alexis von Glasow](https://github.com/vonglasow) for [Inovia](https://github.com/inovia-team)
