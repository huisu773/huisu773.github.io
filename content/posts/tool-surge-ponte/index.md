---
date: '2025-03-18'
draft: false
title: 'Surge Ponte 使用指南'
categories: [Tool]
tags: [Tool,网络]
---

Surge Ponte 是 Surge 推出的内网穿透功能，可以轻松实现在外访问内网。本文介绍**通过代理进行 NAT 穿透**的方法。

Mac 和 Apple TV 的 Surge 可以作为服务端，需要你在这些设备上安装 Surge 并设置 Ponte Device Name。

通过代理进行 NAT 穿透需要有一个支持 **UDP** 的代理，代理名称为 Proxy-Name。

在 Apple TV 上开启 Surge，Ponte Device Name 为 APPLETV。

在配置文件的各部分加入如下内容即可实现 Ponte 的内网穿透。

```conf
[Ponte]
server-proxy-name = Proxy-Name
client-proxy-name = Proxy-Name
[Rule]
DOMAIN-SUFFIX,myhome,DEVICE:APPLETV
[Host]
nas.myhome = 192.168.X.X
```
需要将 `192.168.X.X` 换成内网设备的 IP。

`DOMAIN-SUFFIX,myhome,DEVICE:APPLETV` 放在规则的最前面。

这样，在外就可以通过 `nas.myhome` 访问内网资源。 比如开启了 smb 文件共享，在外就可以接内网 IP 换成 `nas.myhome`，来访问内网的文件了。