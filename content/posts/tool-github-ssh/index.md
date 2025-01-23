---
date: '2025-01-23'
draft: false
title: '将 GitHub ssh 端口改为 443'
categories: [Tool]
tags: [Tool,GitHub,网络]
---

有些代理的 22 端口被阻断了，无法用在 GitHub ssh 上，可以修改 GitHub ssh 端口为 443，以绕过限制：

```bash
Host github.com
  Hostname ssh.github.com
  Port 443
  User git
  IdentityFile ~/.ssh/id_rsa  # 你的私钥路径，如果与默认的不同请进行修改
```

修改完成后测试连接：

```bash
ssh -T git@github.com
```