Role Name
=========

Setting up the Raspberry PI as a NTP server

Requirements
------------

A stable internet connection is required to run a stable NTP server.

Role Variables
--------------

The variable 'timelord' can be used to tell which of the NTP server is leading a pack of Raspberry PI NTP servers.
At this moment not all code is implemented to configure this correctly.
But it will be usefull in the future if you run multiple units behind 1 IPv4 address as not all NTP servers will allow multiple clients from 1 IP address.


Dependencies
------------

I need to check this!

Example Playbook
----------------

You use it like this:
    - hosts: raspberries
      roles:
        - { role: "raspberry_ntp", when: (ntp_server) }

This way you add the ntp_server variable to your inventory for each Raspberry PI that needs to be a NTP server.
If you want to run it on all your Raspberry PI's:

    - hosts: raspberries
      roles:
        - raspberry_ntp


License
-------

BSD

Author Information
------------------

This script was writen as part of automating my homelab.
If you feel it is usefull then let me know.

