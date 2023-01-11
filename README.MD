Overview
--------

This Ansible playbook is designed to automate the installation of Zabbix 6 on Ubuntu 20.04. Zabbix is an open-source monitoring solution that helps you to keep track of the performance and availability of your IT infrastructure.

Requirements
------------

-   Ansible 2.9 or later
-   A Ubuntu 20.04 host to run the playbook on
-   A running MySQL server
-   A user with root or sudo privileges
-   The MySQL root password should be passed as a variable, `mysql_root_password`
-   Zabbix frontend and server configuration, `zabbix.conf.j2`, should be in the same directory

Usage
-----

1.  Clone or download the playbook to your local machine
2.  Edit the `zabbix.conf.j2` file with your specific configurations.
3.  Run the playbook with the command:


`ansible-playbook -i <inventory-file> --extra-vars "mysql_root_password=<root_password>" zabbix-install.yml`

1.  Replace `<inventory-file>` with the path to your inventory file and `<root_password>` with the actual password for the root user of the MySQL server.

What the Playbook Does
----------------------

-   The playbook will add the Zabbix repository to the system.
-   It will install Zabbix server, frontend and agent.
-   Creates a database for Zabbix.
-   Imports the initial schema and data.
-   Configuring PHP-FPM and Apache web server.
-   Start and enable Zabbix and Apache service.

Conclusion
----------

The playbook is intended to be a starting point for your Zabbix installation on Ubuntu 20.04 and will require adjustments to suit your specific needs. Also, it is a good practice to test it in a testing environment before running on production.
