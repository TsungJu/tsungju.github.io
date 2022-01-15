---
layout: post
title: "centos7 user account make install nginx service"
date: 2022-01-14 14:25:06 -0700
comments: true
---

1. Wget lastest nginx .tar.gz file
===================================
```
$ wget --no-check-certificate https://nginx.org/download/nginx-1.19.10.tar.gz
```

2. Extract lastest nginx .tar.gz file
=====================================
```
$ tar xvzf nginx-1.19.10.tar.gz
```

3. Go into extracted nginx folder
==================================
```
$ cd nginx-1.19.10/
```

4. Configure (include prefix path、without http_rewrite_module and http_gzip_module(because without zlib and PCRE library))
===========================================================================================================================
```
$ ./configure --user=leonard --group=leonard --prefix=/home/leonard/nginx --without-http_rewrite_module --without-http_gzip_module
```

5. make and make install
========================
```
$ make
$ make install
```

6. Go into prefix path conf folder and modify nginx.conf port setting bigger than port 1024
============================================================================================
```
$ cd /home/leonard/nginx/conf
$ vi nginx.conf
```

7. Go into prefix path sbin folder and start or stop nginx service
===================================================================
```
$ cd /home/leonard/nginx/sbin
$ ./nginx
$ ./nginx -s stop
```