---
date: '2025-03-02T19:21:18+08:00'
draft: false
title: 'VPS 总结：用过的各种线路的日本VPS'
categories: [VPS]
tags: [VPS,日本VPS]
---

整理一下用过的各种线路的日本 VPS，包括 CN2GIA、CMI、4837、Softbank、IIJ 。

内容仅包括价格（四舍五入）、每月流量、个人使用体验（**仅限电信**），线路是我个人购买时测试出来的，VPS 服务商可能会更换线路；具体的测评数据可以去别的网站上找。

我有独立的东京落地机，线路机主要用来中转、下载和看 YouTube，对线路机的 ip 没有什么特别要求，评价时会额外注意线路机和落地机之间的连接情况。

|产品 | 电信 去程线路/回程线路 | 每月流量 | 价格 | 优点 | 缺点|
|--- | --- | --- | --- | --- | ---|
|DMIT-TYO.Pro.TINY | CN2GIA/CN2GIA | 300 G | 22 USD/M | CN2GIA，线路神；低延迟、低丢包 | 贵（我的缺点）|
|Bandwagon-Osaka-Softbank | CN2GIA/Softbank | 500 G | 46 USD/Y | 平衡价格与线路质量 | 晚高峰少量丢包；大坂东京往返延迟高20|
|V5-Tokyo-Softbank | 163/Softbank | 550 G | 20 CNY/M | 实惠的东京软银 | 晚高峰少量丢包 |
|ZgoCloud-Osaka | IIJ/IIJ | 700 G | 28 USD/Y | 性价比之选 | 晚高峰一般量丢包；大坂东京往返延迟高20；活动时才能买|
|YxVM-Vol | CN2GIA/4837 | 1 T （单向流量） | 3 USD/M | 超性价比之选 | 电信对4837跨网QoS导致晚高峰延迟翻倍|
|Claw | Softbank/Softbank | 500 G （单向流量） | 7 USD/First year | 超级便宜 | 老7刀机，已经绝版；超售太多、晚高峰一般|
|Claw CN-Optimized| 163/4837 | 1 T （单向流量） | 4.2 USD/M | 有性价比的线路机 | 4837 线路，电信会被 QoS；卖的太多、体验一般|
|Bandwagon-Tokyo-CMI | CN2GIA/CMI | 550 G | 73 USD/Y | 想不到 | 贵；CMI跨网QoS|
|GigsGigsCloud | CN2GIA/CN2GIA | 200 G | 12 USD/M | 价格不算太高的CN2GIA；ip也还行 | 一般贵；低配机只有50Mbps；机器性能太差；到落地机延迟30|
|ByteVirt | IIJ/IIJ | 500 G | 30 USD/Y | 性价比；货比较多 | ip经常送中，用不了YT会员；之前偶尔被打的不能用|
|WebARENA Indigo | NTT/NTT | 无限流量 | 460 JPY/M | 双ISP属性的ip；ip干净、解锁非常好的落地机 | 线路绕美，延迟太高；只有100Mbps，想要升级带宽价格就要×4；注册需要日本手机号|