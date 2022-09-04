---
layout: post
title: "Kafka connector can't produce messages troubleshooting"
date: 2021-12-06 14:25:06 -0700
tags: [Kafka]
comments: true
---

Problem Description
===================

若出現Kafka connector無法產生訊息至topic的情況，則可能為connect及connector未正常移除，造成client ID重複，使connector異常，無法產生訊息至topic。

Solution
========

可先移除connector，更改connector name，並再次啟動，則應可恢復。