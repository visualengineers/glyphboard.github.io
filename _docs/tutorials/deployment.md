---
title: Deployment
permalink: /deployment/
---

Currently, the project is deployed on a [HTW Dresden web server](http://itv21.informatik.htw-dresden.de:4200/) using Docker.

### Deploy

Install Docker and Docker-Compose on the host system:

```bash
$ sudo apt-get install docker
$ sudo apt-get install docker-compose
```

Clone the glyphboard repository including the backend submodule, then run docker-compose

```bash
$ git clone https://github.com/visualengineers/glyphboard --recurse-submodules
$ cd glyphboard
$ docker-compose up -d --build
```

### Frontend

Make sure to set the correct backend address in `src/environments/environment.prod.ts`


```typescript
export const environment = {
  production: true,
  backendAddress: 'http://your.server.com:4201/'
};
```

### Backend

You may have to adapt the allowed IPs in the `config.yml` file:

```yaml
base_dir: /
data_folder: data
upload_folder: data
port: 4201
cors: on
allowed_ips:
  - "127.0.0.1"
  - "141.76.66"
  - "141.56"
```
