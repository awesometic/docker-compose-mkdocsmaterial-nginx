## Before run using docker-compose

1. Create Nginx configuration files by executing Nginx once.
```docker
docker run --rm -e PUID=1000 -e PGID=1000 -e TZ=Asia/Seoul --volume /opt/docker/mkdocsmat-nginx:/config -p 8888:80 linuxserver/nginx
```

2. Copy Nginx default server configuration to `config/nginx/site-confs/default`. This makes Nginx as a proxy server that forwards EXTERNAL_PORT to 8000 port of MkDocs-Material

3. Copy MkDocs-Material default configurations to `config/nginx/mkdocsmat/` using `cp -rf` so that making all of the inner files moved. These are the necessary basic configuration files of MkDocs-Material.

4. Then run `docker-compose up -d`

5. If you access to http://server:8888, Nginx server acts as reverse proxy server for MkDocs-Material so that you can see your MkDocs-Material websites.

- [MkDocs](https://www.mkdocs.org/)
- [Material for MkDocs](https://github.com/squidfunk/mkdocs-material)

