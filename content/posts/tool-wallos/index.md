---
date: '2025-03-12'
draft: false
title: '部署 Wallos 管理订阅并添加 https 访问'
categories: [Tool]
tags: [Tool,自部署]
---


Wallos 是一个开源的、自部署的订阅管理软件。
https://github.com/ellite/Wallos

部署 Wallos 需要有一台公网服务器，如果想要https访问还需要有一个域名。

Docker 安装方法参考官网文档：https://docs.docker.com/engine/install/

## 部署 Wallos

新建一个文件夹存放 Wallos 配置文件。

```
mkdir Wallos
cd Wallos
```
新建 docker compose 文件
```
vim docker-compose.yaml
```
按`i`进入输入模式，粘贴如下内容：
```
services:
  wallos:
    container_name: wallos
    image: bellamy/wallos:latest
    ports:
      - "8282:80/tcp"
    environment:
      TZ: 'Asia/Shanghai'
    # Volumes store your data between container upgrades
    volumes:
      - './db:/var/www/html/db'
      - './logos:/var/www/html/images/uploads/logos'
    restart: unless-stopped
```
输入完成后按`Esc`返回命令模式，输入`:wq`保存并退出文件。

运行：
```
docker compose up -d
```
之后应该就可以通过`ip:8282`端口的形式访问了。但是这样只能用http访问，还是不安全。

## 添加https访问

添加https之前需要有一个域名，比如`example.com`，并将域名DNS解析指向服务器ip。

安装certbot：
```
sudo apt install certbot
```

安装完成后为域名申请证书（将`example.com`替换成你自己的域名）：

```
certbot certonly --standalone --email yourmail@mail.com -d example.com
```

安装 nginx ：
```
sudo apt install nginx
```

编辑 nginx 配置文件`/etc/nginx/nginx.conf`（将`example.com`替换成你自己的域名）：
```
pid /var/run/nginx.pid;
worker_processes auto;
worker_rlimit_nofile 51200;
events {
    worker_connections 1024;
    multi_accept on;
    use epoll;
}
http {
    server_tokens off;
    sendfile on;
    tcp_nopush on;
    tcp_nodelay on;
    keepalive_timeout 120s;
    keepalive_requests 10000;
    types_hash_max_size 2048;
    include /etc/nginx/mime.types;
    access_log off;
    error_log /dev/null;

    server {
        listen 80;
        server_name example.com;
        return 301 https://$host$request_uri;
    }

    server {
        listen 443 ssl;
        server_name wallos.huisu.moe;

        ssl_certificate /etc/letsencrypt/live/example.com/fullchain.pem;
        ssl_certificate_key /etc/letsencrypt/live/example.com/privkey.pem;
        ssl_protocols TLSv1.2 TLSv1.3;
        ssl_ciphers HIGH:!aNULL:!MD5;

        location / {
            proxy_pass http://localhost:8282;
            proxy_set_header Host $host;
            proxy_set_header X-Real-IP $remote_addr;
            proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
        }
    }
}

```

部署完成后开启 nginx：
```
sudo nginx -t
sudo systemctl enable nginx
sudo systemctl start nginx
```
之后就可以通过域名+https访问了。