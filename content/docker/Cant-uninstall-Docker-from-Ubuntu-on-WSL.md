---
title: "Cant uninstall Docker from Ubuntu on WSL"
date: 2018-03-02T12:15:19+08:00
draft: false
tags: ["wsl", "docker"]
categories: ["docker"]
subtitle: ""
descriptions: ""
bigimg:
---


Cant uninstall Docker from Ubuntu on WSL

```bash
DESKTOP-APB1HCJ% sudo apt remove docker-ce
Reading package lists... Done
Building dependency tree
Reading state information... Done
The following packages were automatically installed and are no longer required:
  aufs-tools cgroupfs-mount docker-ce-cli libfreetype6 libltdl7 pigz
Use 'sudo apt autoremove' to remove them.
The following packages will be REMOVED:
  docker-ce
0 upgraded, 0 newly installed, 1 to remove and 115 not upgraded.
1 not fully installed or removed.
After this operation, 85.4 MB disk space will be freed.
Do you want to continue? [Y/n] y
dpkg: error processing package docker-ce (--remove):
 package is in a very bad inconsistent state; you should
 reinstall it before attempting a removal
Errors were encountered while processing:
 docker-ce
E: Sub-process /usr/bin/dpkg returned an error code (1)
DESKTOP-APB1HCJ% sudo service docker stop
 * Docker already stopped - file /var/run/docker-ssd.pid not found.
DESKTOP-APB1HCJ% sudo service docker-ce stop
docker-ce: unrecognized service
DESKTOP-APB1HCJ%
```


或者

```bash
DESKTOP-APB1HCJ% sudo apt-get purge docker-ce
Reading package lists... Done
Building dependency tree
Reading state information... Done
The following packages were automatically installed and are no longer required:
  aufs-tools cgroupfs-mount docker-ce-cli libfreetype6 libltdl7 pigz
Use 'sudo apt autoremove' to remove them.
The following packages will be REMOVED:
  docker-ce*
0 upgraded, 0 newly installed, 1 to remove and 115 not upgraded.
1 not fully installed or removed.
After this operation, 85.4 MB disk space will be freed.
Do you want to continue? [Y/n] y
dpkg: error processing package docker-ce (--purge):
 package is in a very bad inconsistent state; you should
 reinstall it before attempting a removal
Errors were encountered while processing:
 docker-ce
E: Sub-process /usr/bin/dpkg returned an error code (1)
DESKTOP-APB1HCJ% sudo apt-get install docker-ce
Reading package lists... Done
Building dependency tree
Reading state information... Done
docker-ce is already the newest version (5:18.09.5~3-0~ubuntu-xenial).
The following package was automatically installed and is no longer required:
  libfreetype6
Use 'sudo apt autoremove' to remove it.
0 upgraded, 0 newly installed, 0 to remove and 115 not upgraded.
1 not fully installed or removed.
Need to get 0 B/17.3 MB of archives.
After this operation, 0 B of additional disk space will be used.
Do you want to continue? [Y/n] y
dpkg: error processing package docker-ce (--configure):
 package is in a very bad inconsistent state; you should
 reinstall it before attempting configuration
Errors were encountered while processing:
 docker-ce
E: Sub-process /usr/bin/dpkg returned an error code (1)
DESKTOP-APB1HCJ%
DESKTOP-APB1HCJ% sudo apt-get -f install
Reading package lists... Done
Building dependency tree
Reading state information... Done
The following package was automatically installed and is no longer required:
  libfreetype6
Use 'sudo apt autoremove' to remove it.
0 upgraded, 0 newly installed, 0 to remove and 115 not upgraded.
1 not fully installed or removed.
Need to get 0 B/17.3 MB of archives.
After this operation, 0 B of additional disk space will be used.
dpkg: error processing package docker-ce (--configure):
 package is in a very bad inconsistent state; you should
 reinstall it before attempting configuration
Errors were encountered while processing:
 docker-ce
E: Sub-process /usr/bin/dpkg returned an error code (1)
```

https://askubuntu.com/questions/148715/how-to-fix-package-is-in-a-very-bad-inconsistent-state-error

sudo dpkg --remove --force-remove-reinstreq 

```bash
DESKTOP-APB1HCJ% sudo dpkg --remove --force-remove-reinstreq  docker-ce
dpkg: warning: overriding problem because --force enabled:
dpkg: warning: package is in a very bad inconsistent state; you should
 reinstall it before attempting a removal
(Reading database ... 29777 files and directories currently installed.)
Removing docker-ce (5:18.09.5~3-0~ubuntu-xenial) ...
invoke-rc.d: could not determine current runlevel
 * Docker already stopped - file /var/run/docker-ssd.pid not found.
DESKTOP-APB1HCJ% dpkg -l | grep docker
rc  docker-ce                        5:18.09.5~3-0~ubuntu-xenial                amd64        Docker: the open-source application container engine
ii  docker-ce-cli                    5:18.09.5~3-0~ubuntu-xenial                amd64        Docker CLI: the open-source application container engine
DESKTOP-APB1HCJ%
```

成功了！






## ref
- https://stackoverflow.com/questions/51377291/cant-uninstall-docker-from-ubuntu-on-wsl
- https://askubuntu.com/questions/148715/how-to-fix-package-is-in-a-very-bad-inconsistent-state-error

