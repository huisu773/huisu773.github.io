---
date: '2025-03-11T19:21:18+08:00'
draft: false
title: 'VPS 简评：日本 WebARENA Indigo VPS'
categories: [VPS]
tags: [VPS,日本VPS,VPS简评]
---

## 简评

日本本土厂商的 WebARENA Indigo 的 VPS，按小时计费，最低配每月上限 449 日元，1c1g 无限流量，峰值带宽 100 Mbps。想要升级带宽就要翻将近 4 倍买每月 1630 的峰值 500 Mbps 的套餐了。

三网绕路，推荐只当作落地 VPS 使用。很好用的落地 VPS，不过晚高峰 v4 国际互联有点炸，推荐打开 v6 获得更好的上网体验。

默认用户名是 centos/ubuntu/debian，强制 ssh key 登陆，ipv6 网络需自行配置。

注册需要 +81 日本手机号。开机需要绑定信用卡，每月自动扣款。

## IP 质量

给一个 ipv4 和一个 ipv6 地址，IP 质量非常好， NTTPC 的 IP，会被很多网站当作真的 ISP。v4 风险有点高，但是 v6 风险非常低，v6 过 Google、Cloudflare 的验证没有任何问题。

解锁需要刷段，有的段解锁全一些。他们家还没遇见能解锁迪士尼的 IP，我自己对一些 Dazn 和 Disney+ 配了 DNS 解锁。

### ipv4

```
########################################################################
一、基础信息（Maxmind 数据库）
自治系统号：            AS2514
组织：                  NTT PC Communications, Inc.
坐标：                  139°41′24″E, 35°41′21″N
地图：                  https://check.place/35.6893,139.6899,15,cn
城市：                  东京都, 东京, 102-0082
使用地：                [JP]日本, [AS]亚洲
注册地：                [JP]日本
时区：                  Asia/Tokyo
IP类型：                 原生IP 
二、IP类型属性
数据库：      IPinfo    ipregistry    ipapi     AbuseIPDB  IP2LOCATION 
使用类型：     家宽        家宽        家宽        家宽        机房    
公司类型：     家宽        家宽        家宽    
三、风险评分
风险等级：      极低         低       中等       高         极高
SCAMALYTICS：                                               100|极高风险
ipapi：                  0.78%|低风险
AbuseIPDB：    0|低风险
IPQS：         0|低风险
Cloudflare：   0|低风险
DB-IP：         |低风险
四、风险因子
库： IP2LOCATION ipapi ipregistry IPQS SCAMALYTICS ipdata IPinfo IPWHOIS
地区：    [US]    [JP]    [JP]    [JP]    [JP]    [JP]    [JP]    [JP]
代理：     否      是      否      否      否      否      否      否 
Tor：      否      否      否      否      否      否      否      否 
VPN：      是      否      是      否      否      无      否      是 
服务器：   是      是      否      无      否      否      否      否 
滥用：     否      否      否      否      无      否      无      无 
机器人：   否      否      无      否      否      无      无      无 
五、流媒体及AI服务解锁检测
服务商：  TikTok   Disney+  Netflix Youtube  AmazonPV  Spotify  ChatGPT 
状态：     解锁     解锁     解锁     解锁     解锁     解锁     解锁   
地区：     [JP]     [SG]     [JP]     [JP]     [JP]     [JP]     [JP]   
方式：     原生      DNS     原生     原生     原生     原生     原生   
六、邮局连通性及黑名单检测
本地25端口：阻断
IP地址黑名单数据库：  有效 439   正常 428   已标记 11   黑名单 0
========================================================================
```

```
============[ Multination ]============
 Dazn:                                  Yes (Region: HK)
 Disney+:                               Yes (Region: SG)
 Netflix:                               Yes (Region: JP)
 YouTube Premium:                       Yes (Region: JP)
 Amazon Prime Video:                    Yes (Region: JP)
 TVBAnywhere+:                          Yes
 Spotify Registration:                  Yes (Region: JP)
 OneTrust Region:                       JP [Tokyo]
 iQyi Oversea Region:                   JP
 Bing Region:                           JP (Risky)
 Apple Region:                          JP
 YouTube CDN:                           [NTTPC] in [Tokyo]
 Netflix Preferred CDN:                 Osaka
 ChatGPT:                               Yes
 Google Gemini:                         Yes (Region: JPN)
 Claude:                                Yes
 Wikipedia Editability:                 Yes
 Google Play Store:                     Japan 
 Google Search CAPTCHA Free:            Yes
 Steam Currency:                        JPY
 ---Forum---
 Reddit:                                No
=======================================
===============[ Japan ]===============
 DMM:                                   Yes
 DMM TV:                                Yes
 Abema.TV:                              Yes (Region: JP)
 Niconico:                              Yes (LiveID: lv346574661)
 Telasa:                                Yes
 U-NEXT:                                Yes
 Hulu Japan:                            Yes
 TVer:                                  Yes
 Lemino:                                No
 AnimeFesta:                            Yes
 WOWOW:                                 Yes
 VideoMarket:                           Yes
 D Anime Store:                         Yes
 FOD(Fuji TV):                          Yes
 Radiko:                                Yes (City: TOKYO)
 Karaoke@DAM:                           Yes
 J:com On Demand:                       Yes
 WATCHA:                                Yes
 Rakuten TV JP:                         Yes
 ---Game---
 Kancolle Japan:                        Yes
 Pretty Derby Japan:                    Yes
 Konosuba Fantastic Days:               Yes
 Princess Connect Re:Dive Japan:        No
 Project Sekai: Colorful Stage:         No
 ---Music---
 Mora:                                  Yes
 music.jp:                              Yes
 ---Forum---
 EroGameSpace:                          Failed (Network Connection)
=======================================
```

### ipv6

```
########################################################################
一、基础信息（Maxmind 数据库）
自治系统号：            AS2514
组织：                  NTT PC Communications, Inc.
坐标：                  139°41′24″E, 35°41′24″N
地图：                  https://check.place/35.69,139.69,14,cn
城市：                  N/A
使用地：                [JP]日本, [AS]亚洲
注册地：                [JP]日本
时区：                  Asia/Tokyo
IP类型：                 原生IP 
二、IP类型属性
数据库：      IPinfo    ipregistry    ipapi     AbuseIPDB  IP2LOCATION 
使用类型：     家宽        家宽        家宽        家宽        家宽    
公司类型：     家宽        家宽        家宽    
三、风险评分
风险等级：      极低         低       中等       高         极高
SCAMALYTICS：  0|低风险
ipapi：    0.00%|极低风险
AbuseIPDB：    0|低风险
IPQS：         0|低风险
Cloudflare：   0|低风险
DB-IP：         |低风险
四、风险因子
库： IP2LOCATION ipapi ipregistry IPQS SCAMALYTICS ipdata IPinfo IPWHOIS
地区：    [JP]    [JP]    [JP]    [JP]    [JP]    [JP]    [JP]    [JP]
代理：     否      否      否      否      否      否      否      否 
Tor：      否      否      否      否      否      否      否      否 
VPN：      否      否      否      否      否      无      否      否 
服务器：   否      是      否      无      否      否      否      否 
滥用：     否      否      否      否      无      否      无      无 
机器人：   否      否      无      否      否      无      无      无 
五、流媒体及AI服务解锁检测
服务商：  TikTok   Disney+  Netflix Youtube  AmazonPV  Spotify  ChatGPT 
状态：     失败     失败     解锁     解锁     屏蔽     解锁     失败   
地区：                       [JP]     [JP]              [JP]            
方式：                       原生     原生              原生            
六、邮局连通性及黑名单检测
本地25端口：阻断
========================================================================
```

```
============[ Multination ]============
 Dazn:                                  IPv6 Is Not Currently Supported
 Disney+:                               IPv6 Is Not Currently Supported
 Netflix:                               Yes (Region: JP)
 YouTube Premium:                       Yes (Region: JP)
 Amazon Prime Video:                    IPv6 Is Not Currently Supported
 TVBAnywhere+:                          IPv6 Is Not Currently Supported
 Spotify Registration:                  Yes (Region: JP)
 OneTrust Region:                       JP [Unknown]
 iQyi Oversea Region:                   IPv6 Is Not Currently Supported
 Bing Region:                           JP (Risky)
 Apple Region:                          JP
 YouTube CDN:                           Tokyo
 Netflix Preferred CDN:                 Tokyo
 ChatGPT:                               Failed (Network Connection)
 Google Gemini:                         Yes (Region: JPN)
 Claude:                                Yes
 Wikipedia Editability:                 Yes
 Google Play Store:                     Japan 
 Google Search CAPTCHA Free:            Yes
 Steam Currency:                        IPv6 Is Not Currently Supported
 ---Forum---
 Reddit:                                IPv6 Is Not Currently Supported
=======================================
===============[ Japan ]===============
 DMM:                                   IPv6 Is Not Currently Supported
 DMM TV:                                IPv6 Is Not Currently Supported
 Abema.TV:                              IPv6 Is Not Currently Supported
 Niconico:                              IPv6 Is Not Currently Supported
 Telasa:                                Yes
 U-NEXT:                                Yes
 Hulu Japan:                            IPv6 Is Not Currently Supported
 TVer:                                  IPv6 Is Not Currently Supported
 Lemino:                                Yes
 AnimeFesta:                            Failed (Network Connection)
 WOWOW:                                 IPv6 Is Not Currently Supported
 VideoMarket:                           IPv6 Is Not Currently Supported
 D Anime Store:                         IPv6 Is Not Currently Supported
 FOD(Fuji TV):                          IPv6 Is Not Currently Supported
 Radiko:                                IPv6 Is Not Currently Supported
 Karaoke@DAM:                           IPv6 Is Not Currently Supported
 J:com On Demand:                       Yes
 WATCHA:                                IPv6 Is Not Currently Supported
 Rakuten TV JP:                         IPv6 Is Not Currently Supported
 ---Game---
 Kancolle Japan:                        IPv6 Is Not Currently Supported
 Pretty Derby Japan:                    Yes
 Konosuba Fantastic Days:               IPv6 Is Not Currently Supported
 Princess Connect Re:Dive Japan:        IPv6 Is Not Currently Supported
 Project Sekai: Colorful Stage:         IPv6 Is Not Currently Supported
 ---Music---
 Mora:                                  IPv6 Is Not Currently Supported
 music.jp:                              IPv6 Is Not Currently Supported
 ---Forum---
 EroGameSpace:                          IPv6 Is Not Currently Supported
=======================================
```

## 线路

电信、联通绕美，移动绕港，直连很难使用：

```
---------------------回程路由--感谢fscarmen开源及PR---------------------
依次测试电信/联通/移动经过的地区及线路，核心程序来自nexttrace，请知悉!
上海电信 202.96.209.133
0.32 ms         AS2514 [InfoSphere] 日本 东京都 nttpc.co.jp
0.55 ms         AS2514 [InfoSphere] 日本 东京都 nttpc.co.jp
1.39 ms         AS2514 [JPNIC-NET] 日本 东京都 东京 nttpc.co.jp
1.49 ms         AS2514 [JPNIC-NET] 日本 东京都 东京 nttpc.co.jp
1.89 ms         AS6453 [TATA-COMMUNICATIONS] 日本 东京都 东京 tatacommunications.com
119.07 ms       AS6453 [TATA-COMMUNICATIONS] 日本 东京都 东京 tatacommunications.com
118.59 ms       AS6453 日本 东京都 东京 tatacommunications.com
* ms    AS6453 [TATA-COMMUNICATIONS] 日本 东京都 东京 tatacommunications.com
* ms    AS6453 [TATA-COMMUNICATIONS] 日本 千叶 tatacommunications.com
113.14 ms       AS6453 美国 加利福尼亚 洛杉矶 tatacommunications.com
303.24 ms       AS6453 美国 加利福尼亚 洛杉矶 tatacommunications.com
168.14 ms       AS4134 [CHINANET-BB] 中国 上海 www.chinatelecom.com.cn 电信
上海联通 210.22.97.1
0.29 ms         AS2514 [InfoSphere] 日本 东京都 nttpc.co.jp
1.82 ms         AS2514 [InfoSphere] 日本 东京都 nttpc.co.jp
1.31 ms         AS2514 [JPNIC-NET] 日本 东京都 东京 nttpc.co.jp
1.37 ms         AS2514 [JPNIC-NET] 日本 东京都 东京 nttpc.co.jp
1.75 ms         AS6453 [TATA-COMMUNICATIONS] 日本 东京都 东京 tatacommunications.com
114.77 ms       AS6453 [TATA-COMMUNICATIONS] 日本 东京都 东京 tatacommunications.com
109.26 ms       AS6453 日本 东京都 东京 tatacommunications.com
165.28 ms       AS6453 [TATA-COMMUNICATIONS] 日本 千叶 tatacommunications.com
159.71 ms       AS6453 美国 加利福尼亚 洛杉矶 tatacommunications.com
164.84 ms       AS4837 [CU169-BACKBONE] 中国 北京 chinaunicom.cn 联通
158.41 ms       AS4837 [CU169-BACKBONE] 中国 北京 chinaunicom.cn
182.41 ms       AS17621 [CNCNET-SH] 中国 上海 闵行区 chinaunicom.cn 联通
上海移动 211.136.112.200
0.33 ms         AS2514 [InfoSphere] 日本 东京都 nttpc.co.jp
0.56 ms         AS2514 [InfoSphere] 日本 东京都 nttpc.co.jp
1.11 ms         AS2514 [JPNIC-NET] 日本 东京都 东京 nttpc.co.jp
1.35 ms         AS2514 [JPNIC-NET] 日本 东京都 东京 nttpc.co.jp
1.71 ms         AS6453 [TATA-COMMUNICATIONS] 日本 东京都 东京 tatacommunications.com
46.57 ms        AS6453 [TATA-COMMUNICATIONS] 日本 东京都 东京 tatacommunications.com
50.17 ms        AS6453 日本 东京都 东京 tatacommunications.com
* ms    AS6453 [TATA-COMMUNICATIONS] 日本 东京都 东京 tatacommunications.com
44.99 ms        AS6453 [TATAC-ARIN] 日本 东京都 东京 tatacommunications.com
48.44 ms        AS6453 [TATA-COMMUNICATIONS] 日本 东京都 东京 tatacommunications.com
* ms    AS6453 [TATA-COMMUNICATIONS] 中国 香港 tatacommunications.com
50.30 ms        AS6453 [TATA-COMMUNICATIONS] 中国 香港 tatacommunications.com
* ms    AS6453 [TATA-COMMUNICATIONS] 中国 香港 tatacommunications.com
* ms    AS9808 [CMNET] 中国 上海 X-I chinamobileltd.com 移动
* ms    AS9808 [CMNET] 中国 上海 chinamobileltd.com
195.09 ms       AS24400 [CMNET] 中国 上海 sh.10086.cn 移动
158.06 ms       AS24400 [CMNET] 中国 上海 浦东新区 sh.10086.cn 移动
------------------------------------------------------------------------
```