# Single URL Docker Registry UI for Docker Swarm

Traefik v3 with Let's Encrypt for Public PULLs and Authenticated PUSHes and Secure Dashboard

## Introduction

This configuration file will serve both a container registry and Joxit's Docker-Registry-UI on the same
domain over HTTPS that can be secured with certificates from Let's Encrypt.  The registry allows for
public PULLs and authenticated PUSHes.

Additionally, the **traefik** dashboard UI is published (although you do not need it during production).

## Prerequisites

### `.env` File

The `.env` file makes it easy to perform all the replacements necessary.

```shell
DOMAIN=contoso.com
EMAIL=postmaster@contoso.com
```

### `traefik` network

Prior to bringing the stack, create the `traefik` network manually.

```shell
❯ docker network create --driver=overlay traefik
a1tzlg1kecmsfpt8oawnv18bb
```

## Uppies

```shell
❯ docker stack deploy -c swarm.yml registry
Updating service registry_redis (id: okqye8d2on72k26e0l2rpumn4)
Updating service registry_registry (id: p11pag7vp3ziarq0kmth2srgl)
Updating service registry_ui (id: nbdjifilcczwq5a9len6ydzy7)
Updating service registry_traefik (id: 6wqawq10rehxxd5b54ehli92m)
```
