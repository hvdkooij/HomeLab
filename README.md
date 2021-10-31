# HomeLab

My Homelab. Building and maintaining my homelab with Ansible

Mainly a bunch of Raspberry PI's.
But I expect to add some other stuff as well as soon as I get remote access to it.

## Requirements

Some of the requirements are listed below.
Not all requirements may apply to all roles.

 - Raspberry PI's are installed with Ubuntu.
 - Hosts run SSH server.
 - Initial setup was completed.
 - User can sudo without password.

## Notes

The NTP servers are intended to be reachable over the internet and hardened accordingly.
The NTP role has a special feature as I have only 1 IPv4 address.
Some server can't handle multiple clients through NAT.
So the timelord variable allows you to specify which of the servers has the benefit of more NTP stratum 1 peers.

## Disclaimer

This is an experimental repository created and maintained by Hugo van der Kooij <hugo@vanderkooij.org>

Updates may occur whenever I feel like it. This may be influence by weather conditions.

