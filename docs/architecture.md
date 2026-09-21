# Architecture

## Overview

The home lab uses a repurposed HP laptop as a headless Ubuntu Server
named `node01`.

Administration is performed from a Windows ThinkPad over the local
network.

```text
Windows ThinkPad
     |
     | SSH
     | Wake-on-LAN Magic Packet
     v
Home Router
     |
     | Ethernet
     v
node01 - Ubuntu Server
     |
     +-- Nginx
     +-- Docker
     |
     +-- K3s
          |
          +-- Kubernetes Deployment
          |      |
          |      +-- Nginx Pod
          |
          +-- ConfigMap
          |      |
          |      +-- index.html
          |
          +-- NodePort Service
                 |
                 +-- TCP 30928 -> 80
