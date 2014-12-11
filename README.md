storm
=========

The role do following:

1. Setup java 6 (open jdk)
2. Setup user and group for Apache Storm
3. Install Apache Storm
4. Configure Apache Storm

This role does not running storm.

Build status
------------
![Build Status](https://travis-ci.org/anorsich/ansible-storm.svg?branch=master)


Requirements
------------

--


Role Variables
--------------

Defaults are:

    storm_version: apache-storm-0.9.3
    storm_user: storm
    storm_group: storm
    storm_uid: 3060
    storm_gid: 3060

    storm_zookeeper_servers:
      - "localhost"
    storm_zookeeper_port: 2181
    storm_nimbus_host: "localhost"
    storm_nimbus_childopts: "-Xmx1024m -Djava.net.preferIPv4Stack=true"
    storm_ui_childopts: "-Xmx768m -Djava.net.preferIPv4Stack=true"
    storm_ui_port: 8086
    storm_supervisor_childopts: "-Djava.net.preferIPv4Stack=true"
    storm_worker_childopts: "-Xmx768m -Djava.net.preferIPv4Stack=true"
    storm_supervisor_slots_ports:
      - "6700"
      - "6701"
      - "6702"
      - "6703"
    storm_local_dir: /var/storm



Dependencies
------------

Depends on [smola.java](https://galaxy.ansible.com/list#/roles/1209).
requirements.txt file for ansible-galaxy can be found in tests dir.

Example Playbook
----------------

    - hosts: servers
      roles:
         - { role: anorsich.storm, storm_version: apache-storm-0.9.3 }

License
-------

BSD
