---
date: '2025-03-01T19:21:18+08:00'
draft: false
title: 'VPS 简评：ZgoCloud 日本大阪 IIJ VPS（Osaka AMD Ryzen9 Performance VPS - Specials - Lite ）'
categories: [VPS]
tags: [VPS,日本VPS,VPS简评]
---

## 简评

年付 28 USD 的大阪 VPS，每月 700 G 双向流量，峰值带宽 200 Mbps，三网 IIJ 线路，上游xTom，移动电信可用，联通不可用。算是有性价比的日本线路产品。

## IP 质量

给一个 ipv4 地址，广播 IP，IP 质量和解锁都挺一般的。

```
########################################################################
一、基础信息（Maxmind 数据库）
自治系统号：            AS4785
组织：                  xTom
坐标：                  135°30′2″E, 34°41′35″N
地图：                  https://check.place/34.693,135.5005,15,cn
城市：                  Osaka, Osaka, 543-0062
使用地：                [JP]日本, [AS]亚洲
注册地：                [DE]德国
时区：                  Asia/Tokyo
IP类型：                 广播IP 
二、IP类型属性
数据库：      IPinfo    ipregistry    ipapi     AbuseIPDB  IP2LOCATION 
使用类型：     机房        机房        机房        机房        机房    
公司类型：     机房        机房        机房    
三、风险评分
风险等级：      极低         低       中等       高         极高
SCAMALYTICS：  0|低风险
ipapi：                  0.78%|低风险
AbuseIPDB：    0|低风险
IPQS：                        75|可疑IP
Cloudflare：   0|低风险
DB-IP：         |低风险
四、风险因子
库： IP2LOCATION ipapi ipregistry IPQS SCAMALYTICS ipdata IPinfo IPWHOIS
地区：    [JP]    [JP]    [JP]    [JP]    [JP]    [JP]    [JP]    [JP]
代理：     否      否      否      是      否      否      否      否 
Tor：      否      否      否      否      否      否      否      否 
VPN：      否      否      否      是      否      无      否      否 
服务器：   是      是      是      无      否      否      是      是 
滥用：     否      否      否      否      无      否      无      无 
机器人：   否      否      无      否      否      无      无      无 
五、流媒体及AI服务解锁检测
服务商：  TikTok   Disney+  Netflix Youtube  AmazonPV  Spotify  ChatGPT 
状态：     解锁     屏蔽    仅自制    解锁     解锁     屏蔽     解锁   
地区：     [JP]              [JP]     [JP]     [JP]              [JP]   
方式：     原生              原生     原生     原生              原生   
六、邮局连通性及黑名单检测
本地25端口：阻断
IP地址黑名单数据库：  有效 439   正常 426   已标记 13   黑名单 0
========================================================================
```

```
============[ Multination ]============
 Dazn:                                  Failed (Error: )
 Disney+:                               No (IP Banned By Disney+ 1)
 Netflix:                               Originals Only
 YouTube Premium:                       Yes (Region: JP)
 Amazon Prime Video:                    Yes (Region: JP)
 TVBAnywhere+:                          Yes
 Spotify Registration:                  No
 OneTrust Region:                       JP [Osaka]
 iQyi Oversea Region:                   JP
 Bing Region:                           JP (Risky)
 Apple Region:                          JP
 YouTube CDN:                           Osaka
 Netflix Preferred CDN:                 Osaka
 ChatGPT:                               Yes
 Google Gemini:                         Yes (Region: JPN)
 Claude:                                Yes
 Wikipedia Editability:                 No
 Google Play Store:                     Japan 
 Google Search CAPTCHA Free:            Yes
 Steam Currency:                        JPY
 ---Forum---
 Reddit:                                No
=======================================
===============[ Japan ]===============
 DMM:                                   Yes
 DMM TV:                                No
 Abema.TV:                              No
 Niconico:                              No (Official Live Unavailable. LiveID: lv346511920)
 Telasa:                                No
 U-NEXT:                                Yes
 Hulu Japan:                            No
 TVer:                                  Yes
 Lemino:                                Yes
 AnimeFesta:                            No
 WOWOW:                                 No
 VideoMarket:                           Yes
 D Anime Store:                         No
 FOD(Fuji TV):                          Yes
 Radiko:                                Yes (City: TOKYO)
 Karaoke@DAM:                           Yes
 J:com On Demand:                       Yes
 WATCHA:                                Yes
 Rakuten TV JP:                         No
 ---Game---
 Kancolle Japan:                        Yes
 Pretty Derby Japan:                    Failed (Network Connection)
 Konosuba Fantastic Days:               Yes
 Princess Connect Re:Dive Japan:        Failed (Network Connection)
 Project Sekai: Colorful Stage:         No
 ---Music---
 Mora:                                  Yes
 music.jp:                              No
 ---Forum---
 EroGameSpace:                          Yes
=======================================
```

## 线路

24小时延迟及丢包（from vps789.com）：

![from vps789.com](<jp-zgo.png>)

三网回程路由：

```
---------------------回程路由--感谢fscarmen开源及PR---------------------
依次测试电信/联通/移动经过的地区及线路，核心程序来自nexttrace，请知悉!
上海电信 202.96.209.133
0.49 ms         AS4785 德国 北莱茵－威斯特法伦州 杜塞尔多夫 xtom.com
8.27 ms         AS4785 [OWL-JP] 日本 大阪府 大阪市 xtom.com
0.28 ms         AS4785 [OWL-JP] 日本 大阪府 大阪市 xtom.com
0.51 ms         AS2497 [JPNIC-NET] 日本 东京都 东京 iij.ad.jp
0.57 ms         AS2497 [JPNIC-NET] 日本 东京都 东京 iij.ad.jp
2.33 ms         AS2497 [IIJ] 日本 大阪府 大阪 iij.ad.jp
11.42 ms        AS2497 [IIJ] 日本 东京都 东京 iij.ad.jp
9.92 ms         AS2497 [IIJ] 日本 东京都 东京 iij.ad.jp
8.38 ms         * [CHINANET-FJ] 日本 东京都 东京 电信
37.71 ms        AS4134 [CHINANET-BB] 中国 上海 www.chinatelecom.com.cn 电信
41.46 ms        AS4812 [CHINANET-SH] 中国 上海 chinatelecom.cn 电信
上海联通 210.22.97.1
0.86 ms         AS4785 德国 北莱茵－威斯特法伦州 杜塞尔多夫 xtom.com
22.05 ms        AS4785 [OWL-JP] 日本 大阪府 大阪市 xtom.com
0.85 ms         AS4785 [OWL-JP] 日本 大阪府 大阪市 xtom.com
0.73 ms         AS2497 [JPNIC-NET] 日本 东京都 东京 iij.ad.jp
0.51 ms         AS2497 [JPNIC-NET] 日本 东京都 东京 iij.ad.jp
1.02 ms         AS2497 [IIJ] 日本 大阪府 大阪 iij.ad.jp
* ms    AS2497 [IIJ] 日本 东京都 东京 iij.ad.jp
24.89 ms        AS2497 [JPNIC-NET] 日本 东京都 东京 iij.ad.jp
82.08 ms        AS4837 [CU169-BACKBONE] 中国 上海 X-I chinaunicom.cn 联通
71.54 ms        AS4837 [CU169-BACKBONE] 中国 上海 chinaunicom.cn 联通
* ms    AS17621 [UNICOM-SH] 中国 上海 chinaunicom.cn 联通
80.66 ms        AS17621 [APNIC-AP] 中国 上海 chinaunicom.cn 联通
79.17 ms        AS17621 [CNCNET-SH] 中国 上海 闵行区 chinaunicom.cn 联通
上海移动 211.136.112.200
0.71 ms         AS4785 德国 北莱茵－威斯特法伦州 杜塞尔多夫 xtom.com
13.12 ms        AS4785 [OWL-JP] 日本 大阪府 大阪市 xtom.com
0.38 ms         AS4785 [OWL-JP] 日本 大阪府 大阪市 xtom.com
0.56 ms         AS2497 [JPNIC-NET] 日本 东京都 东京 iij.ad.jp
0.48 ms         AS2497 [JPNIC-NET] 日本 东京都 东京 iij.ad.jp
0.77 ms         AS2497 [IIJ] 日本 大阪府 大阪 iij.ad.jp
20.32 ms        AS2497 [IIJ] 日本 东京都 东京 iij.ad.jp
10.08 ms        AS2497 [JPNIC-NET] 日本 东京都 东京 iij.ad.jp
59.63 ms        AS9808 [CMNET] 中国 上海 X-I chinamobileltd.com 移动
62.21 ms        AS9808 [CMNET] 中国 上海 I-C chinamobileltd.com 移动
48.05 ms        AS9808 [CMNET] 中国 上海 chinamobileltd.com 移动
63.59 ms        AS24400 [CMNET] 中国 上海 sh.10086.cn 移动
48.86 ms        AS24400 [CMNET] 中国 上海 浦东新区 sh.10086.cn 移动
------------------------------------------------------------------------
```
