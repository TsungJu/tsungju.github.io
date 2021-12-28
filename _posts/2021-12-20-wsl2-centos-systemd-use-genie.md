---
layout: post
title: "WSL2 centos install genie use systemd"
date: 2021-12-20 14:25:06 -0700
comments: true
---

1. install dotnet-sdk
=====================
```
$ dnf install dotnet-sdk-5.0
```

2. Install epel-release and daemonize
=====================================
```
$ yum install epel-release
$ yum install daemonize
```

3. Create and edit genie.ini
============================
```
$ vim /etc/genie.ini
```
## content:
```
[genie]
secure-path=/lib/systemd:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
unshare=/usr/bin/unshare
update-hostname=true
clone-path=false
clone-env=WSL_DISTRO_NAME,WSL_INTEROP,WSLENV,DISPLAY,WAYLAND_DISPLAY,PULSE_SERVER
systemd-timeout=240
resolved-stub=false
```

4. Clone arkane-systems/genie repo. and make install
====================================================
```
$ git clone https://github.com/arkane-systems/genie.git
$ cd genie
$ make
$ make install-local
```

5. genie command
================
```
$ genie -c <command> #啟動systemd進程，並執行相應的指令
```