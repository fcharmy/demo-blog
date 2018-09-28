---
title: Blind Spot of myself
layout: default
comments: true
---

Summary of blind spot of myself in cs, I suddenly understand why other people are outerstanding.

* How dockker layers works?
  - layers are reusable
  - every command specify in your docker file will cause your previous image to change which create a new layer
  - if you change your docker file, only that layer and after this layer will be changed
  - each container is an image with a readable/writeable layer on top of a bunch of read-only layers, like FROM ubuntu:15.04, these layers for ubuntu is read only, and on top of this we add a contain layer to write data
 
* Marathon service discovery
  - **Mesos DNS** provides service discovery through the domain name system.
  - **Marathon-lb** provides port-based service discovery using HAProxy, a lightweight TCP/HTTP proxy.
 
* API read limit
  - Leaky Bucket (Nginx limit_req)
  - Token Bucket (Guava RateLimiter)
  - Redis counter expire in 1s

* Why Airflow?
  some important feature for me, [all great things about Airflow](https://gtoonstra.github.io/etl-with-airflow/great.html)
  - Jobs can pass parameters to other jobs downstream
  - built-in authentication details
  - Accessibility of log files and other meta-data through the web GUI
  - Dynamic DAGs
  - Conditional execution in job flow diagrams
  - Detailed info about landing times, processing times and SLA misses
  - Temporarily turning workflows on and off
  - Easy to re-run processing
  - AJAX/Rest API for job manipulation
  - Work gets distributed across your cluster at the task level, not at the DAG level
