===
hostsfile
===

Formula to set up name resolution for all members of a salt cluster in /etc/hosts

.. note::

    See the full `Salt Formulas installation and usage instructions
    <http://docs.saltstack.com/topics/conventions/formulas.html>`_.

Available states
================

.. contents::
    :local:

``hostsfile``
-------

Uses the salt mine function __network.ip_addrs__ to add minion ids and their regarding ips to the local hosts file.
This works best if the minion id is the fqdn and (if the machines have more than one interface) the desired interface to use
for this is configured with the mine function::

    mine_functions:
      network.interfaces: []
      network.ip_addrs:
        - eth1
    mine_interval: 2

``hostsfile.hostname``
--------------

Also set and persist the hostname (again - using the minion id). This has so far been most useful on EC2 instances.

Works on RedHat/CentOS 5.X or RedHat/CentOS 6.X and Amazon OS - should also work on Ubuntu/Debian.
