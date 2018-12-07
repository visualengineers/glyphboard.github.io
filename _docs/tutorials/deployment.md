---
title: Deployment
permalink: /deployment/
---

Currently, the project is deployed on a TU Dresden web server using [Ajenti V](http://ajenti.org/). There must be a new Ajenti Website such as `glyphboard.mediadesign-tud.de` with Website fiels `/srv/websites/glyphboardmediadesign-tudde`.

### Build

Deployment package is locally build using the production environment:

```bash
$ ng build --prod
```

Or a specific build environment such as:

```bash
$ ng build --configuration=medical
```

SSH to App-Server and `git clone git@gitlab.mg.inf.tu-dresden.de:vanda/glyphboard.git` (add SSH-Key from server to project first).

Upload files from `dist` folder to new Ajenti Website via FTP user (root directory). Or build directly on server and copy contents of `dist` to root folder.

### Frontend

Add new `Static files` Content in Ajenti website:

* URL Pattern: `/` (Exact)

For Authentication see [online tutorial](https://www.digitalocean.com/community/tutorials/how-to-set-up-password-authentication-with-nginx-on-ubuntu-14-04) for server setup.

```bash
$ sudo sh -c "echo -n 'user_name:' >> /etc/ajenti/.htpasswd"
$ sudo sh -c "openssl passwd -apr1 >> /etc/ajenti/.htpasswd"
```

Add *Custom Configuration* in *Ajenti Website* under *Static Files*

```
auth_basic "Restricted Content";
auth_basic_user_file /etc/ajenti/.htpasswd;
```

### Backend

For backend, install new Ajenti Task:

```
cd /srv/websites/glyphboardmediadesign-tudde/glyphboard/ && python backend/server.py
```

And Ajenti Job that executes the task on reboot. Open Terminal window in Ajenti and install Python libs for Ajenti run user:

```bash
& cd /srv/websites/glyphboardmediadesign-tudde/glyphboard/backend
$ pip install -r requirements.txt
```

Create `Reverse Proxy` content in Ajenti website of glyphboard:

* URL Pattern: `/backend` (Exact)
* URL: `http://localhost:4201`

Add *Custom configuration* under *Advanced*:

```bash
rewrite ^/backend/(.*)$ /$1 break;
client_max_body_size 5M;
```
