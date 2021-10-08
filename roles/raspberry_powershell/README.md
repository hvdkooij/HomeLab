Role Name
=========

Tis role will install the requested version of PowerShell on you Raspberry PI's.

Requirements
------------

This role requires internet access to donwload the PowerShell code from internet.

Role Variables
--------------

The following variable are available to tinker with the version you install and where to install it on your Raspebbery PI's.

	pwsh_path	Where to install Powershell
	pwsh_ver	The version of PowerShell to install
	temp_path	Where to store temporary files

The following variable is based on the value of pwsh_ver and is something you should most likely not change.
Make sure you read the code before you try something like that.

	pwsh_pkg	The exact package to download to your Rasberry PI's.

The defaults are:
    pwsh_path: /usr/local/powershell
    pwsh_ver: 7.1.4
    pwsh_pkg: powershell-{{ pwsh_ver }}-linux-arm64.tar.gz
    temp_path: /tmp


Dependencies
------------

No external requirements needed.

Example Playbook
----------------

Use it like:

    - hosts: raspberries
      roles:
        - raspberry_powershell

License
-------

BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
