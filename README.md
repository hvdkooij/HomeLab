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

I added a playbook do-dist-upgrade.yml to do a distribution upgrade. Feel free to use it or adapt it as needed.


## Examples

### Distribution upgrade

Example run upgrading multiple Raspberry PI units from Ubunto 21.10 to 22.04

```~/git/HomeLab $ ansible-playbook  do-dist-upgrade.yml -i inventory/hosts 

PLAY [raspberries] *********************************************************************************

TASK [Preflight version] ***************************************************************************
ok: [pi400]
ok: [pi31]
ok: [pi25]
ok: [pi26]

TASK [debug] ***************************************************************************************
ok: [pi25] => {
    "lsb_release.stdout": "Distributor ID:\tUbuntu\nDescription:\tUbuntu 21.10\nRelease:\t21.10\nCodename:\timpish"
}
ok: [pi26] => {
    "lsb_release.stdout": "Distributor ID:\tUbuntu\nDescription:\tUbuntu 21.10\nRelease:\t21.10\nCodename:\timpish"
}
ok: [pi31] => {
    "lsb_release.stdout": "Distributor ID:\tUbuntu\nDescription:\tUbuntu 21.10\nRelease:\t21.10\nCodename:\timpish"
}
ok: [pi400] => {
    "lsb_release.stdout": "Distributor ID:\tDebian\nDescription:\tDebian GNU/Linux 11 (bullseye)\nRelease:\t11\nCodename:\tbullseye"
}

TASK [APT update and upgrade] **********************************************************************
skipping: [pi400]
ok: [pi31]
ok: [pi25]
ok: [pi26]

TASK [Install update-manager-core if needed] *******************************************************
skipping: [pi400]
ok: [pi31]
ok: [pi25]
ok: [pi26]

TASK [Now run the releaese upgrade command] ********************************************************
skipping: [pi400]
changed: [pi31]
changed: [pi25]
changed: [pi26]

TASK [Reboot] **************************************************************************************
skipping: [pi400]
changed: [pi31]
changed: [pi25]
changed: [pi26]

TASK [Postflight version] **************************************************************************
skipping: [pi400]
changed: [pi31]
changed: [pi25]
changed: [pi26]

TASK [debug] ***************************************************************************************
ok: [pi25] => {
    "lsb_release.stdout": "Distributor ID:\tUbuntu\nDescription:\tUbuntu 22.04 LTS\nRelease:\t22.04\nCodename:\tjammy"
}
ok: [pi26] => {
    "lsb_release.stdout": "Distributor ID:\tUbuntu\nDescription:\tUbuntu 22.04 LTS\nRelease:\t22.04\nCodename:\tjammy"
}
ok: [pi31] => {
    "lsb_release.stdout": "Distributor ID:\tUbuntu\nDescription:\tUbuntu 22.04 LTS\nRelease:\t22.04\nCodename:\tjammy"
}
skipping: [pi400]

PLAY RECAP *****************************************************************************************
pi25                       : ok=8    changed=3    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0   
pi26                       : ok=8    changed=3    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0   
pi31                       : ok=8    changed=3    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0   
pi400                      : ok=2    changed=0    unreachable=0    failed=0    skipped=6    rescued=0    ignored=0 
```

## Disclaimer

This is an experimental repository created and maintained by Hugo van der Kooij <hugo@vanderkooij.org>

Updates may occur whenever I feel like it. This may be influence by weather conditions.

