---
date: '2025-03-09T19:21:18+08:00'
draft: false
title: 'VPS 简评：搬瓦工美国 DC9 CN2GIA&CMIN2'
categories: [VPS]
tags: [VPS,美国VPS,VPS简评]
---

## 简评

搬瓦工之前出的 35 刀一年的 DC9 套餐，每月 750 G 双向流量，电信联通回程 CN2GIA，移动回程 CMIN2，原先也算不错的产品，但是最近被更实惠的新套餐背刺了？

## IP 质量

给一个 ipv4 地址，IP 质量差，有一些流媒体解锁。最近送了一个 ipv6 地址，但是不走优化线路，懒得测了。

```
########################################################################
一、基础信息（Maxmind 数据库）
自治系统号：            AS25820
组织：                  IT7NET
坐标：                  118°16′15″W, 34°3′5″N
地图：                  https://check.place/34.0515,-118.2707,15,cn
城市：                  加州, 洛杉矶, 90017
使用地：                [US]美国, [NA]北美洲
注册地：                [CA]加拿大
时区：                  America/Los_Angeles
IP类型：                 广播IP 
二、IP类型属性
数据库：      IPinfo    ipregistry    ipapi     AbuseIPDB  IP2LOCATION 
使用类型：     机房        机房        家宽        机房        机房    
公司类型：     机房        机房        家宽    
三、风险评分
风险等级：      极低         低       中等       高         极高
SCAMALYTICS：  0|低风险
ipapi：         0.31%|低风险
AbuseIPDB：    0|低风险
IPQS：                                          87|存在风险
Cloudflare：   0|低风险
DB-IP：         |低风险
四、风险因子
库： IP2LOCATION ipapi ipregistry IPQS SCAMALYTICS ipdata IPinfo IPWHOIS
地区：    [US]    [US]    [US]    [US]    [US]    [US]    [US]    [US]
代理：     否      否      否      是      否      否      否      否 
Tor：      否      否      否      否      否      否      否      否 
VPN：      是      是      是      是      否      无      否      是 
服务器：   是      是      是      无      否      是      是      是 
滥用：     否      否      否      是      无      否      无      无 
机器人：   否      否      无      否      否      无      无      无 
五、流媒体及AI服务解锁检测
服务商：  TikTok   Disney+  Netflix Youtube  AmazonPV  Spotify  ChatGPT 
状态：     解锁     屏蔽    仅自制    解锁     解锁     屏蔽     解锁   
地区：     [US]              [US]     [US]     [US]              [US]   
方式：     原生              原生     原��     原生               DNS   
六、邮局连通性及黑名单检测
本地25端口：阻断
IP地址黑名单数据库：  有效 439   正常 425   已标记 14   黑名单 0
========================================================================
```

```
============[ Multination ]============
 Dazn:                                  Failed (Error: )
 Disney+:                               No (IP Banned By Disney+ 1)
 Netflix:                               Originals Only
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
 Wikipedia Editability:                 No
 Google Play Store:                     United States 
 Google Search CAPTCHA Free:            Yes
 Steam Currency:                        USD
 ---Forum---
 Reddit:                                No
=======================================
===========[ North America ]===========
 Paramount+:                            Yes (Region: US)
 Discovery+:                            Yes (Region: US)
 Acorn TV:                              Yes
 BritBox:                               Yes
 SonyLiv:                               Failed (Network Connection)
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
 Hulu:                                  No
 NFL+:                                  Yes
 ESPN+:[Sponsored by Jam]               No
 MGM+:                                  No
 Starz:                                 No
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
 Meta AI:                               Failed (Error: PAGE ERROR)
 ---CA---
 HotStar:                               No (Discontinued in the US)
 CBC Gem:                               No
 Crave:                                 No
=======================================
```

## 线路

电信联通回程 CN2GIA，移动回程 CMIN2：

```
---------------------回程路由--感谢fscarmen开源及PR---------------------
依次测试电信/联通/移动经过的地区及线路，核心程序来自nexttrace，请知悉!
上海电信 202.96.209.133
12.44 ms        * RFC1918
4.46 ms         * RFC1918
0.40 ms         AS25820 美国 加利福尼亚州 洛杉矶 it7.net
120.89 ms       * [CN2-BackBone] 中国 上海 X-I chinatelecom.cn 电信
125.24 ms       * [CN2-BackBone] 中国 上海 chinatelecom.cn 电信
132.01 ms       * [CN2-BackBone] 中国 上海 I-C chinatelecom.cn 电信
126.84 ms       AS4812 [CHINANET-SH] 中国 上海 chinatelecom.cn 电信
128.15 ms       AS4812 [CHINANET-SH] 中国 上海 chinatelecom.cn 电信
127.25 ms       AS4812 [CHINANET-SH] 中国 上海 chinatelecom.cn 电信
上海联通 210.22.97.1
16.68 ms        * RFC1918
37.45 ms        * RFC1918
0.81 ms         AS25820 美国 加利福尼亚州 洛杉矶 it7.net
128.03 ms       * [CN2-BackBone] 中国 上海 X-I chinatelecom.cn 电信
128.67 ms       * [CN2-BackBone] 中国 上海 chinatelecom.cn 电信
178.72 ms       * [CN2-BackBone] 中国 上海 chinatelecom.cn 电信
177.73 ms       AS4837 [CU169-BACKBONE] 中国 上海 chinaunicom.cn 联通
153.98 ms       AS17621 [APNIC-AP] 中国 上海 chinaunicom.cn 联通
154.81 ms       AS17621 [CNCNET-SH] 中国 上海 闵行区 chinaunicom.cn 联通
上海移动 211.136.112.200
28.66 ms        * RFC1918
5.08 ms         * RFC1918
0.46 ms         AS25820 美国 加利福尼亚州 洛杉矶 it7.net
0.83 ms         AS25820 美国 加利福尼亚州 洛杉矶 it7.net
126.59 ms       AS58807 [CMIN2-NET] 美国 加利福尼亚 洛杉矶 cmi.chinamobile.com 移动
126.42 ms       AS58807 [CMIN2-NET] 中国 上海 cmi.chinamobile.com 移动
128.68 ms       AS9808 [CMNET] 中国 上海 chinamobileltd.com 移动
128.10 ms       AS9808 [CMNET] 中国 上海 chinamobileltd.com 移动
127.96 ms       AS9808 [CMNET] 中国 上海 chinamobileltd.com
234.24 ms       AS9808 [CMNET] 中国 上海 chinamobileltd.com
131.15 ms       AS24400 [CMNET] 中国 上海 sh.10086.cn 移动
130.81 ms       AS24400 [CMNET] 中国 上海 浦东新区 sh.10086.cn 移动
------------------------------------------------------------------------
```