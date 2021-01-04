EdgeOS ZeroTier
===============

This is repo DOES NOT replace original work from Dennis Kruyt.  It is merely a
remix, of his work, for my own use.

Copied from
  * https://kruyt.org/zerotier-on-edgerouter-p2/
  * https://github.com/dkruyt/resources/raw/master/zerotier-edgeos.tgz

Changes from dkruyt version:
  * Un-archive tgz in order to track changes to individual files (+ expose them to pull requests)

Instructions
------------

Install ZeroTier on EdgeRouter:

```admin@edgeos:~$ sudo -i
root@edgeos:~# curl -s https://install.zerotier.com | sudo bash

*** ZeroTier One Quick Install for Unix-like Systems

*** Tested distributions and architectures:
***   MacOS (10.7+) on x86_64 (just installs ZeroTier One.pkg)
***   Debian (7+) on x86_64, x86, arm, and arm64
***   RedHat/CentOS (6+) on x86_64 and x86
***   Fedora (16+) on x86_64 and x86
***   SuSE (12+) on x86_64 and x86
***   Mint (18+) on x86_64, x86, arm, and arm64

*** Please report problems to contact@zerotier.com and we will try to fix.

*** Detecting Linux Distribution

*** Found Debian "stretch" (or similar), creating /etc/apt/sources.list.d/zerotier.list
OK

*** Installing zerotier-one package...
Get:1 http://download.zerotier.com/debian/stretch stretch InRelease [33.6 kB]
Get:2 http://download.zerotier.com/debian/stretch stretch/main mipsel Packages [2823 B]
Fetched 36.4 kB in 1s (19.2 kB/s)
Reading package lists... Done
Reading package lists... Done
Building dependency tree... Done
The following NEW packages will be installed:
  zerotier-one
0 upgraded, 1 newly installed, 0 to remove and 0 not upgraded.
Need to get 728 kB of archives.
After this operation, 2631 kB of additional disk space will be used.
Get:1 http://download.zerotier.com/debian/stretch stretch/main mipsel zerotier-one mipsel 1.6.2-2 [728 kB]
Fetched 728 kB in 0s (1658 kB/s)
debconf: delaying package configuration, since apt-utils is not installed
Selecting previously unselected package zerotier-one.
(Reading database ... 37095 files and directories currently installed.)
Preparing to unpack .../zerotier-one_1.6.2-2_mipsel.deb ...
Unpacking zerotier-one (1.6.2-2) ...
Setting up zerotier-one (1.6.2-2) ...
Created symlink /etc/systemd/system/multi-user.target.wants/zerotier-one.service -> /lib/systemd/system/zerotier-one.service.Processing triggers for systemd (232-25+deb9u12) ...

*** Enabling and starting zerotier-one service...
Synchronizing state of zerotier-one.service with SysV service script with /lib/systemd/systemd-sysv-install.
Executing: /lib/systemd/systemd-sysv-install enable zerotier-one

*** Waiting for identity generation...

*** Success! You are ZeroTier address [ 471a6527a0 ].

root@edgeos:~#
```

Re-install likely needed after firmware upgrades.

Install CLI commands:

```
root@edgeos:~# curl -LO https://github.com/gsfjohnson/edgeos-zerotier/archive/2.0.9.tar.gz
root@edgeos:~# tar xvzf 2.0.9.tar.gz --exclude='*.md' --strip-components=1 -C /
```