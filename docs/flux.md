---
title: NGINX
parent: Supporting Services
grand_parent: Architecture
layout: page
---

[ingress-nginx is an Ingress controller for Kubernetes using NGINX as a reverse proxy and load balancer.](https://github.com/kubernetes/ingress-nginx).

## Development
The following repositories relate to our implementation of this component:
* [Flux](https://github.com/lsc-sde/iac-flux-nginx)

## Network Policies

```mermaid
flowchart LR
    all([all services]) -->|Ingress ALL| svc[nginx] 
    svc --> all
```

| Direction | Ports/Type | Description |
| --- | --- | --- |
| Ingress | All | Allows all traffic inbound. TODO: This needs to be refined |
| Egress | All | Allows all traffic outbound. TODO: This needs to be refined |