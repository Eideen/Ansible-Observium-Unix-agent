Ansible Observium Unix agent
=========

Role to install Observium Unix agent on Linux.

Will remove undefine scripts.

If lighttpd is used it will modify `10-status.conf` to enable monitoring.


Requirements
------------

* None

Role Variables
--------------
* observium_agent_client_IP: Defines what host is allowed to connect over telnet. accepts:
  - 192.168.0.0 # range
  - 192.168.0.1/24 # subnet range
  - 192.168.0.2 # Singel IP
  - 192.168.0.2 192.168.2.0 # combination of address's.
* agent_packages: Defines a list of packages to be installed as part of the role
* agent_additional_packages: Is a user/playlist defines list.
* agent_director: Where the script are installed
* agent_scripts: normally defined in vars/
* agent_additional_scripts: Is a user/playlist defines list.

Any script not listed by `agent_scripts` and `agent_additional_scripts`, is removed. Only works with files.


Dependencies
------------

- None

Example Playbook
----------------
````
- hosts: observium-targes
      roles:
         - { role: ansible-observium-unixagent,
           x: 42 }
      vars:
        agent_additional_scripts: ['hddtemp', 'mysql']
        observium_agent_client_IP: 192.168.2.8
````
License
-------

GPL-2.0-or-later

Author Information
------------------

role author: Torstein Eide
git-repository:
