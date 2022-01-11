---
layout: post
title: "flask-jwt-extended decode token keyError:'identity'"
date: 2022-01-07 15:25:06 -0700
comments: true
---

Problem Description
===================

使用flask-jwt-extended的decode_token功能，將token decode，並取出create_access_token時的identity，如下code snippet，顯示 KeyError:'identity'。
```
decode_token(token)['identity']
```

Solution
========

新版flask-jwt-extended已將identity替換為sub，因此取create_access_token時的identity，需改用sub，如下code snippet。
```
decode_token(token)['sub']
```