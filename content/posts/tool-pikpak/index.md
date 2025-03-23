---
date: '2025-03-20T19:00:00+08:00'
draft: false
title: 'Pikpak 分流策略'
categories: [Tool]
tags: [Tool,网络]
---

Pikpak 是一个在线网盘，主域名屏蔽了中国大陆的 IP，但是下载域名没有限制。可以通过分流策略实现功能正常使用和客户端下载流量走直连。

在配置文件中加入如下的分流策略即可：

```
DOMAIN,mypikpak.com,Proxy
DOMAIN,mypikpak.net,Proxy
DOMAIN,user.mypikpak.com,Proxy
DOMAIN,access.mypikpak.com,Proxy
DOMAIN,api-drive.mypikpak.com,Proxy
DOMAIN-SUFFIX,mypikpak.com,Direct
DOMAIN-SUFFIX,mypikpak.net,Direct
```