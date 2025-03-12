---
date: '2025-03-12T19:21:18+08:00'
draft: false
title: 'VPS 简评：ZgoCloud 美国 9929&CMIN2'
categories: [VPS]
tags: [VPS,美国VPS,VPS简评]
---

## 简评

ZgoCloud 活动时推出的一年 25 刀的美西套餐，每月 600 G 双向流量，峰值带宽 200 Mbps，电信、联通回程走 9929，移动回程走 CMIN2。

对于移动和联通来说是非常不错的机子，对于电信要看本地有没有跨网 QoS。虽然 9929 也是精品线路，但是有些地区的电信会对联通的线路进行跨网 QoS，导致延迟增加、速度受限。

ZgoCloud 家的 IP 质量非常不错，算是兼顾 IP 与线路的机器了。但是，虽然在一些数据库里是家宽/ISP属性，但是还是会被一些自建 IP 库的大厂当成 Hosting 对待。

## IP 质量

IP 质量非常不错，解锁也很全。

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
SCAMALYTICS：  0|低风险
ipapi：           0.39%|低风险
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
服务器：   是      否      否      无      否      否      否      否 
滥用：     否      否      否      否      无      否      无      无 
机器人：   否      否      无      否      否      无      无      无 
五、流媒体及AI服务解锁检测
服务商：  TikTok   Disney+  Netflix Youtube  AmazonPV  Spotify  ChatGPT 
状态：     解锁     解锁     解锁     解锁     解锁     屏蔽     解锁   
地区：     [US]     [US]     [US]     [US]     [US]              [US]   
方式：     原生     原生     原生     原生     原生              原生   
六、邮局连通性及黑名单检测
本地25端口：阻断
IP地址黑名单数据库：  有效 439   正常 426   已标记 13   黑名单 0
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
 SonyLiv:                               Yes (Region: US)
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
 ESPN+:[Sponsored by Jam]               Yes
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

电信、联通回程 9929，移动回程 CMIN2：

```
---------------------回程路由--感谢fscarmen开源及PR---------------------
依次测试电信/联通/移动经过的地区及线路，核心程序来自nexttrace，请知悉!
上海电信 202.96.209.133
1.67 ms         AS8796 美国 加利福尼亚 洛杉矶 kurun.com
0.66 ms         * RFC1918
0.82 ms         * RFC1918
16.38 ms        AS10099 [CUG-BACKBONE] 美国 加利福尼亚 洛杉矶 chinaunicomglobal.com 联通
135.74 ms       AS10099 [CUG-BACKBONE] 美国 加利福尼亚 洛杉矶 chinaunicomglobal.com 联通
135.74 ms       AS9929 [CNC-BACKBONE] 中国 上海 chinaunicom.cn 联通 CUII
136.77 ms       AS9929 [CNC-BACKBONE] 中国 上海 chinaunicom.cn 联通 CUII
139.01 ms       AS4134 [CHINANET-BB] 中国 上海 www.chinatelecom.com.cn 电信
187.54 ms       AS4134 [CHINANET-BB] 中国 上海 www.chinatelecom.com.cn 电信
144.70 ms       AS4812 [CHINANET-SH] 中国 上海 chinatelecom.cn 电信
139.90 ms       AS4812 [CHINANET-SH] 中国 上海 chinatelecom.cn 电信
137.23 ms       AS4812 [CHINANET-SH] 中国 上海 chinatelecom.cn 电信
上海联通 210.22.97.1
1.51 ms         AS8796 美国 加利福尼亚 洛杉矶 kurun.com
2.65 ms         * RFC1918
1.01 ms         * RFC1918
1.31 ms         AS10099 [CUG-BACKBONE] 美国 加利福尼亚 洛杉矶 chinaunicomglobal.com 联通
133.29 ms       AS10099 [CUG-BACKBONE] 中国 香港 chinaunicomglobal.com 联通
132.68 ms       AS9929 [CNC-BACKBONE] 中国 上海 chinaunicom.cn 联通 CUII
133.54 ms       AS9929 [CNC-BACKBONE] 中国 上海 chinaunicom.cn 联通 CUII
261.56 ms       AS4837 [CU169-BACKBONE] 中国 上海 chinaunicom.cn 联通
158.38 ms       AS17621 [CNCNET-SH] 中国 上海 闵行区 chinaunicom.cn 联通
上海移动 211.136.112.200
9.30 ms         AS8796 美国 加利福尼亚 洛杉矶 kurun.com
0.58 ms         * RFC1918
11.13 ms        * RFC1918
20.97 ms        AS58807 [CMIN2-NET] 美国 加利福尼亚 洛杉矶 cmi.chinamobile.com 移动
126.85 ms       AS58807 [CMIN2-NET] 美国 加利福尼亚 洛杉矶 cmi.chinamobile.com 移动
126.28 ms       AS58807 [CMIN2-NET] 中国 上海 cmi.chinamobile.com 移动
126.44 ms       AS9808 [CMNET] 中国 上海 chinamobileltd.com 移动
126.37 ms       AS9808 [CMNET] 中国 上海 chinamobileltd.com 移动
128.03 ms       AS9808 [CMNET] 中国 上海 chinamobileltd.com
128.88 ms       AS24400 [CMNET] 中国 上海 sh.10086.cn 移动
155.07 ms       AS24400 [CMNET] 中国 上海 浦东新区 sh.10086.cn 移动
------------------------------------------------------------------------
```