---
description: >-
  Medkey HIS can be installed using Docker on any platform: Linux, Windows, Mac
  OS
---

# Installing using Docker

Hospital Information System Medkey support Docker installation and deployment. You can easily run latest built distributive of Medkey, or clone repository and run Docker container using source code.

This guide will provide you how to install Medkey using Docker on Linux and Windows environment.

## Prerequisites

* Installed Docker 18.09 or higher, accessible using `docker` command, tested Docker execution of Docker containers on this machine
* Installed Docker Compose 1.24 or higher, accessible using `docker-compose` command
* For installation from repository: installed git-scm program, accessible using `git` command 
* For installation using .tar.gz distribution: installed tar program, accessible using `tar` command

## Installation steps

Execute commands below using repository \(require installed git\) or .tar.gz distribution.

{% tabs %}
{% tab title="Using repository" %}
```
git clone git@github.com:medkey-org/medkey.git
cd medkey
docker-compose up -d --build && docker-compose exec mk /bin/bash -c "cd /var/www/medkey && composer install && cp .env.prod .env && php bin config-database/pg-uuid-activate && php bin migrate --interactive=0 && php bin seed Package && cd frontend && npm install && npm run build-prod" 
```
{% endtab %}

{% tab title="Using .tar.gz distribution" %}
```
tar -zxvf medkey.tar.gz
cd medkey
docker-compose up -d --build && docker-compose exec mk /bin/bash -c "cd /var/www/medkey && composer install && cp .env.prod .env && php bin config-database/pg-uuid-activate && php bin migrate --interactive=0 && php bin seed Package && cd frontend && npm install && npm run build-prod" 
```
{% endtab %}
{% endtabs %}

## Installation check

1. Run browser, open URL `http://127.0.0.1:8090` \(if you need to check ports used by docker container — run command `docker-compose ps`\)
2. Login using credentials: login `admin`, password `admin`

