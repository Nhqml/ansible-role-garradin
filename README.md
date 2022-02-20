Garradin
=========

Ansible role to install [Garradin](https://garradin.eu/) on a Debian machine.

Requirements
------------

You must be admin of the target machine.

Role Variables
--------------

* `garradin_package_url`: URL of the `.deb` package of Garradin to install (see [this page](https://fossil.kd2.org/garradin/uvlist))
* `server_name`: name of the server (e.g. `garradin.example.com`)
* `icon`: icon to display
* `favicon`: favicon to use
* `additional_config`: additional Garradin config (appended to `/usr/share/garradin/config.local.php`)
* `server_name`: name of the server (e.g. `garradin.example.com`)

Dependencies
------------

None.

Example Playbook
----------------

    - name: Setup Garradin
    hosts: debian

    gather_facts: no

    roles:
      - role: garradin
      become: yes
      vars:
        server_name: garradin.example.com
        icon: files/icon.png
        favicon: files/favicon.png
        additional_config: |
          const PREFER_HTTPS = true;
          const ENABLE_UPGRADES = false;

License
-------

GPL-3.0-or-later
