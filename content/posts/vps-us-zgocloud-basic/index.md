---
date: '2025-03-09T19:21:18+08:00'
draft: false
title: 'VPS 简评：ZgoCloud 美国 VPS 普通线路（Los Angeles Global VPS - Specials - Basic）'
categories: [VPS]
tags: [VPS,美国VPS,VPS简评]
---

## 简评

ZgoCloud 活动限时售卖的美西落地机，9.9 刀一年每月 1 T 流量，12.9 刀一年每月 1.5 T 流量，15 刀一年每月 2 T 流量。三网普通线路直连，能用但是不如优化线路极致。

IP 质量是一大亮点，风险低解锁多。不过虽然在一些数据库里是家宽/ISP属性，但是还是会被一些自建 IP 库的大厂当成 Hosting 对待。。

## IP 质量

IP 质量好，解锁多。

```
########################################################################
一、基础信息（Maxmind 数据库）
自治系统号：            AS8796
组织：                  FD-298-8796
坐标：                  118°14′38″W, 34°3′16″N
地图：                  https://check.place/34.0544,-118.244,15,cn
城市：                  加州, 洛杉矶, 90060
使用地：                [US]美国, [NA]北美洲
注册地：                [US]美国
时区：                  America/Los_Angeles
IP类型：                 原生IP 
二、IP类型属性
数据库：      IPinfo    ipregistry    ipapi     AbuseIPDB  IP2LOCATION 
使用类型：     家宽        家宽        其他        家宽        机房    
公司类型：     商业        家宽        其他    
三、风险评分
风险等级：      极低         低       中等       高         极高
SCAMALYTICS：               23|低风险
ipapi：    0.02%|极低风险
AbuseIPDB：    0|低风险
IPQS：         0|低风险
Cloudflare：   0|低风险
DB-IP：         |低风险
四、风险因子
库： IP2LOCATION ipapi ipregistry IPQS SCAMALYTICS ipdata IPinfo IPWHOIS
地区：    [US]    [US]    [US]    [US]    [US]    [US]    [US]    [US]
代理：     否      否      否      否      否      否      否      否 
Tor：      否      否      否      否      否      否      否      否 
VPN：      否      否      否      否      否      无      否      否 
服务器：   是      是      否      无      否      否      否      否 
滥用：     否      否      否      否      无      否      无      无 
机器人：   否      否      无      否      否      无      无      无 
五、流媒体及AI服务解锁检测
服务商：  TikTok   Disney+  Netflix Youtube  AmazonPV  Spotify  ChatGPT 
状态：     解锁     解锁     解锁     解锁     解锁     屏蔽     解锁   
地区：     [US]     [US]     [US]     [US]     [US]              [US]   
方式：     原生     原生     原生     原生     原生              原生   
六、邮局连通性及黑名单检测
本地25端口：阻断
IP地址黑名单数据库：  有效 439   正常 424   已标记 13   黑名单 2
========================================================================
```

```
============[ Multination ]============
 Dazn:                                  Yes (Region: US)
 Disney+:                               Yes (Region: US)
 Netflix:                               Yes (Region: US)
 YouTube Premium:                       Yes (Region: US)
 Amazon Prime Video:                    Yes (Region: US)
 TVBAnywhere+:                          Yes
 Spotify Registration:                  No
 OneTrust Region:                       US [California]
 iQyi Oversea Region:                   US
 Bing Region:                           US (Risky)
 Apple Region:                          US
 YouTube CDN:                           Los Angeles, CA
 Netflix Preferred CDN:                 Los Angeles, CA
 ChatGPT:                               Yes
 Google Gemini:                         Yes (Region: USA)
 Claude:                                Yes
 Wikipedia Editability:                 Yes
 Google Play Store:                     United States 
 Google Search CAPTCHA Free:            Yes
 Steam Currency:                        USD
 ---Forum---
 Reddit:                                Yes
=======================================
===========[ North America ]===========
 Paramount+:                            Yes (Region: US)
 Discovery+:                            Yes (Region: US)
 Acorn TV:                              Yes
 BritBox:                               Yes
 SonyLiv:                               No (EPDblocked API)
 NBA TV:                                Yes
 TLC GO:                                Yes (Region: US)
 Shudder:                               Yes
 Fubo TV:                               Yes (Region:US)
 Tubi TV:                               Yes
 Pluto TV:                              Yes
 KOCOWA:                                Yes
 AMC+:                                  Yes (Region: USA)
 MathsSpot Roblox:                      Failed (Error: FailureUnauthorized)
 ---US---
 FOX:                                   Yes
 Hulu:                                  Yes
 NFL+:                                  Yes
 ESPN+:[Sponsored by Jam]               No
 MGM+:                                  No
 Starz:                                 Yes
 Philo:                                 Yes
 FXNOW:                                 Yes
 HBO Max:                               Yes (Region: US)
 Crackle:                               Yes
 CW TV:                                 Yes
 A&E TV:                                Yes
 NBC TV:                                Yes
 Sling TV:                              Yes
 encoreTVB:                             Yes
 Peacock TV:                            Yes
 Popcornflix:                           Failed (Network Connection)
 Crunchyroll:                           Yes
 Directv Stream:                        Yes
 Meta AI:                               No
 ---CA---
 HotStar:                               No (Discontinued in the US)
 CBC Gem:                               No
 Crave:                                 No
=======================================
```

## 线路

三网直的普通线路：

```
---------------------回程路由--感谢fscarmen开源及PR---------------------
依次测试电信/联通/移动经过的地区及线路，核心程序来自nexttrace，请知悉!
上海电信 202.96.209.133
2.25 ms         AS8796 美国 加利福尼亚 洛杉矶 kurun.com
0.75 ms         * RFC1918
1.16 ms         AS1299 [ARELION-NET] 美国 加利福尼亚 洛杉矶 arelion.com
172.58 ms       AS1299 [ARELION-NET] 美国 加利福尼亚 洛杉矶 Telia-CT-Peer arelion.com
131.17 ms       AS4134 [CHINANET-BB] 中国 上海 www.chinatelecom.com.cn 电信
138.65 ms       AS4134 [CHINANET-BB] 中国 上海 www.chinatelecom.com.cn 电信
132.95 ms       AS4134 [CHINANET-BB] 中国 上海 www.chinatelecom.com.cn 电信
154.95 ms       AS4812 [CHINANET-SH] 中国 上海 闵行 chinatelecom.cn
144.53 ms       AS4812 [CHINANET-SH] 中国 上海 chinatelecom.cn 电信
上海联通 210.22.97.1
1.94 ms         AS8796 美国 加利福尼亚 洛杉矶 kurun.com
0.86 ms         * RFC1918
1.06 ms         AS1299 [ARELION-NET] 美国 加利福尼亚 洛杉矶 arelion.com
0.64 ms         AS1299 [ARELION-NET] 美国 加利福尼亚 洛杉矶 arelion.com
13.52 ms        AS1299 美国 加利福尼亚 洛杉矶 arelion.com
156.57 ms       AS4837 [CU169-BACKBONE] 中国 北京 chinaunicom.cn 联通
149.55 ms       AS4837 [CU169-BACKBONE] 中国 北京 chinaunicom.cn 联通
206.30 ms       AS4837 [CU169-BACKBONE] 中国 北京 chinaunicom.cn 联通
172.00 ms       AS17621 [APNIC-AP] 中国 上海 chinaunicom.cn 联通
169.21 ms       AS17621 [CNCNET-SH] 中国 上海 闵行区 chinaunicom.cn 联通
上海移动 211.136.112.200
1.90 ms         AS8796 美国 加利福尼亚 洛杉矶 kurun.com
12.86 ms        * RFC1918
10.00 ms        AS58453 [CMI-INT] 美国 加利福尼亚 洛杉矶 cmi.chinamobile.com
1.09 ms         AS58453 [CMI-INT] 美国 加利福尼亚 洛杉矶 cmi.chinamobile.com 移动
133.54 ms       AS58453 [CMI-INT] 中国 上海 cmi.chinamobile.com
143.83 ms       AS9808 [CMNET] 中国 上海 X-I chinamobileltd.com 移动
178.94 ms       AS9808 [CMNET] 中国 上海 chinamobileltd.com 移动
232.75 ms       AS9808 [CMNET] 中国 上海 chinamobileltd.com
------------------------------------------------------------------------
```