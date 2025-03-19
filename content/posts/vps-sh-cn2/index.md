---
date: '2025-03-20'
draft: false
title: '上海 CN2 NAT 测试'
categories: [VPS]
tags: [VPS,上海VPS]
---

上海 CN2 线路也是久仰大名了，出国流量自动走 CN2 GIA，正要有一家在卖上海 cn2 nat，79 一个月 200 G 双向流量，正好买来试一试。

用 nexttrace 测了一下线路，测试结果有点不尽如人意。

## 香港

到谷歌 GCP 香港：

```
traceroute to 34.150.84.19, 30 hops max, 52 bytes payload, ICMP mode
1   10.0.0.254      *                         RFC1918          
                                              0.22 ms / 0.14 ms / 0.23 ms
2   180.169.18.161  AS4812   [CHINANET-SH]    中国 上海市  黄浦 chinatelecom.cn  电信
                                              1.37 ms / 1.26 ms / 1.36 ms
3   172.16.0.2      *                         RFC1918          
                                              2.73 ms / 2.19 ms / 2.09 ms
4   203.156.240.90  AS4812                    中国 上海市   chinatelecom.cn  电信
                                              105.04 ms / * ms / * ms
5   10.200.200.5    *                         RFC1918          
                                              11.58 ms / 4.49 ms / 4.64 ms
6   180.169.17.165  AS4812   [CHINANET-SH]    中国 上海 上海  chinatelecom.cn 
                                              1.73 ms / 1.64 ms / 1.64 ms
7   58.40.245.25    AS4812                    中国 上海  奉贤区 chinatelecom.cn  电信
                                              1.81 ms / 1.50 ms / 1.52 ms
8   61.129.146.190  AS4812                    中国 上海 上海  chinatelecom.cn 
                                              1.62 ms
    61.129.147.58   AS4812                    中国 上海 上海  chinatelecom.cn 
                                              1.52 ms
    61.129.147.190  AS4812                    中国 上海 上海  chinatelecom.cn 
                                              1.72 ms
9   101.95.89.97    AS4812   [CHINANET-SH]    中国 上海   chinatelecom.cn  电信
                                              3.33 ms
    101.95.89.41    AS4812   [CHINANET-SH]    中国 上海   chinatelecom.cn  电信
                                              2.03 ms / * ms
10  101.95.89.98    AS4812   [CHINANET-SH]    中国 上海   chinatelecom.cn  电信
                                              9.43 ms / 2.34 ms / 2.32 ms
11  *
12  *
13  59.43.39.190    *        [CN2-BackBone]   中国 上海  I-X chinatelecom.cn  电信
                                              103.17 ms / * ms / * ms
14  59.43.188.230   *        [CN2-BackBone]   中国 香港   chinatelecom.cn  电信
                                              29.99 ms / 30.11 ms / 30.16 ms
15  203.131.241.65  AS2914   [NTT-GLOBAL]     中国 香港   gin.ntt.net 
    xe-2-5-3-2.a01.chwahk03.hk.bb.gin.ntt.net   27.64 ms / 27.02 ms / 26.97 ms
16  129.250.4.127   AS2914   [NTT-BACKBONE]   中国 香港   gin.ntt.net 
    ae-2.a02.chwahk03.hk.bb.gin.ntt.net       27.19 ms / 27.16 ms / 27.12 ms
17  129.250.4.124   AS2914   [NTT-BACKBONE]   中国 香港   gin.ntt.net 
    ae-2.a00.chwahk03.hk.bb.gin.ntt.net       27.46 ms / 27.63 ms / 27.74 ms
18  203.131.250.82  AS2914   [NTT-GLOBAL]     中国 香港   gin.ntt.net 
                                              27.32 ms / 27.25 ms / 27.28 ms
19  34.150.84.19    AS396982                  中国 香港   google.com 
    19.84.150.34.bc.googleusercontent.com     66.89 ms / 65.08 ms / 64.70 ms
```

到亚马逊 AWS 香港：

```
traceroute to 16.163.131.38, 30 hops max, 52 bytes payload, ICMP mode
1   10.0.0.254      *                         RFC1918          
                                              0.43 ms / 0.21 ms / 0.23 ms
2   180.169.18.161  AS4812   [CHINANET-SH]    中国 上海市  黄浦 chinatelecom.cn  电信
                                              1.50 ms / 1.36 ms / 1.42 ms
3   172.16.0.2      *                         RFC1918          
                                              3.84 ms / 2.01 ms / 2.39 ms
4   *
5   10.200.200.5    *                         RFC1918          
                                              3.67 ms / 3.53 ms / 4.37 ms
6   180.169.17.165  AS4812   [CHINANET-SH]    中国 上海 上海  chinatelecom.cn 
                                              18.43 ms / 12.07 ms / 2.08 ms
7   58.40.245.25    AS4812                    中国 上海  奉贤区 chinatelecom.cn  电信
                                              2.25 ms / 1.56 ms / 1.63 ms
8   61.129.146.58   AS4812                    中国 上海 上海  chinatelecom.cn 
                                              1.80 ms
    61.129.147.62   AS4812                    中国 上海 上海  chinatelecom.cn 
                                              2.10 ms
    61.129.146.186  AS4812                    中国 上海 上海  chinatelecom.cn 
                                              1.76 ms
9   101.95.89.97    AS4812   [CHINANET-SH]    中国 上海   chinatelecom.cn  电信
                                              53.46 ms / * ms / * ms
10  101.95.89.98    AS4812   [CHINANET-SH]    中国 上海   chinatelecom.cn  电信
                                              2.65 ms / * ms / * ms
11  *
12  *
13  *
14  59.43.249.29    *        [CN2-Global]     中国 香港   chinatelecom.cn  电信
                                              27.01 ms / 26.95 ms / 27.22 ms
15  203.131.241.65  AS2914   [NTT-GLOBAL]     中国 香港   gin.ntt.net 
                                              27.31 ms / 27.22 ms / 27.19 ms
16  *
17  *
18  *
19  *
20  *
21  *
22  *
23  *
24  *
25  *
26  *
27  *
28  *
29  *
30  *
```

到微软 Azure 香港：

```
traceroute to 20.24.72.70, 30 hops max, 52 bytes payload, ICMP mode
1   10.0.0.254      *                         RFC1918          
                                              0.20 ms / 0.14 ms / 0.17 ms
2   180.169.18.161  AS4812   [CHINANET-SH]    中国 上海市  黄浦 chinatelecom.cn  电信
                                              4.13 ms / 1.33 ms / 10.63 ms
3   172.16.0.2      *                         RFC1918          
                                              3.03 ms / 2.14 ms / 2.05 ms
4   203.156.240.90  AS4812                    中国 上海市   chinatelecom.cn  电信
                                              6.05 ms / * ms / * ms
5   10.200.200.5    *                         RFC1918          
                                              3.38 ms / 8.89 ms / 18.27 ms
6   180.169.17.165  AS4812   [CHINANET-SH]    中国 上海 上海  chinatelecom.cn 
                                              2.68 ms / 2.33 ms / 2.81 ms
7   58.40.245.25    AS4812                    中国 上海  奉贤区 chinatelecom.cn  电信
                                              1.95 ms / 1.51 ms / 1.59 ms
8   61.129.147.198  AS4812                    中国 上海   chinatelecom.cn  电信
                                              1.96 ms
    61.129.146.198  AS4812                    中国 上海   chinatelecom.cn  电信
                                              1.92 ms
    61.129.146.194  AS4812                    中国 上海   chinatelecom.cn  电信
                                              2.01 ms
9   61.129.146.197  AS4812                    中国 上海 上海  chinatelecom.cn 
                                              9.19 ms / 6.11 ms / 4.12 ms
10  101.95.89.62    AS4812   [CHINANET-SH]    中国 上海   chinatelecom.cn  电信
                                              6.09 ms / 3.64 ms / 8.66 ms
11  *
12  *
13  *
14  59.43.189.82    *        [CN2-BackBone]   中国 广东 广州 I-Х chinatelecom.cn  电信
                                              32.06 ms / 32.14 ms / 32.05 ms
15  63.216.143.45   AS3491                    中国 香港   pccwglobal.com 
                                              32.98 ms / 31.65 ms / 32.79 ms
16  63.218.174.122  AS3491   [PCCW-BACKBONE]  中国 香港   pccwglobal.com 
    BE41.br04.hkg12.as3491.net                31.73 ms / 31.55 ms / * ms
17  63.216.176.146  AS3491                    中国 香港   pccwglobal.com 
    63-216-176-146.static.as3491.net          65.32 ms / 65.14 ms / 65.21 ms
18  104.44.42.196   AS8075   [MSFT]           中国 香港   microsoft.com 
    ae26-0.icr02.hkg31.ntwk.msn.net           63.24 ms / 63.04 ms / 66.38 ms
19  *
20  *
21  *
22  *
23  *
24  *
25  *
26  *
27  *
28  *
29  *
30  *
```

到阿里云香港：

```
traceroute to 47.238.240.49, 30 hops max, 52 bytes payload, ICMP mode
1   10.0.0.254      *                         RFC1918          
                                              0.15 ms / 0.15 ms / 0.13 ms
2   180.169.18.161  AS4812   [CHINANET-SH]    中国 上海市  黄浦 chinatelecom.cn  电信
                                              1.48 ms / 2.11 ms / 5.58 ms
3   172.16.0.2      *                         RFC1918          
                                              5.35 ms / 52.34 ms / * ms
4   203.156.240.90  AS4812                    中国 上海市   chinatelecom.cn  电信
                                              6.04 ms / * ms / * ms
5   10.200.200.5    *                         RFC1918          
                                              3.39 ms / 3.46 ms / 15.99 ms
6   180.169.17.165  AS4812   [CHINANET-SH]    中国 上海 上海  chinatelecom.cn 
                                              616.86 ms / 566.99 ms / 517.21 ms
7   58.40.245.25    AS4812                    中国 上海  奉贤区 chinatelecom.cn  电信
                                              1.90 ms / 1.53 ms / 2.06 ms
8   61.129.146.190  AS4812                    中国 上海 上海  chinatelecom.cn 
                                              1.74 ms
    61.129.146.58   AS4812                    中国 上海 上海  chinatelecom.cn 
                                              1.71 ms
    61.129.147.62   AS4812                    中国 上海 上海  chinatelecom.cn 
                                              1.73 ms
9   *
10  101.95.89.70    AS4812   [CHINANET-SH]    中国 上海   chinatelecom.cn  电信
                                              103.53 ms / * ms / * ms
11  *
12  59.43.130.202   *        [CN2-BackBone]   中国 上海  C-I chinatelecom.cn  电信
                                              * ms / 3.68 ms / 53.75 ms
13  *
14  59.43.248.238   *        [CN2-Global]     中国 香港   chinatelecom.cn  电信
                                              29.90 ms / 30.21 ms / 29.47 ms
15  63.218.211.65   AS3491   [PCCW-BACKBONE]  中国 香港   pccwglobal.com 
                                              28.49 ms / 28.52 ms / 28.52 ms
16  63.218.114.82   AS3491   [PCCW-BACKBONE]  中国 香港   pccwglobal.com 
    Hu-0-0-0-11.clbr02.hkg04.as3491.net       78.91 ms / * ms / * ms
17  63.216.84.146   AS3491                    中国 香港   pccwglobal.com 
    taobao.hu0-0-0-8.clbr02.hkg04.as3491.net   27.51 ms / 27.63 ms / 27.73 ms
18  *
19  *
20  *
21  *
22  47.238.240.49   AS45102                   中国 香港   alibabagroup.com 
                                              32.85 ms / 32.75 ms / 32.71 ms
```

## 台湾

到谷歌 GCP 台湾绕港：

```
traceroute to 34.80.25.50, 30 hops max, 52 bytes payload, ICMP mode
1   10.0.0.254      *                         RFC1918          
                                              0.21 ms / 0.15 ms / 0.20 ms
2   180.169.18.161  AS4812   [CHINANET-SH]    中国 上海市  黄浦 chinatelecom.cn  电信
                                              1.48 ms / 1.32 ms / 12.12 ms
3   172.16.0.2      *                         RFC1918          
                                              2.83 ms / 2.11 ms / 2.28 ms
4   203.156.240.90  AS4812                    中国 上海市   chinatelecom.cn  电信
                                              54.88 ms / 55.26 ms / * ms
5   10.200.200.5    *                         RFC1918          
                                              5.68 ms / 3.29 ms / 3.42 ms
6   180.169.17.165  AS4812   [CHINANET-SH]    中国 上海 上海  chinatelecom.cn 
                                              1.69 ms / 1.67 ms / 4.28 ms
7   58.40.245.25    AS4812                    中国 上海  奉贤区 chinatelecom.cn  电信
                                              7.14 ms / 1.48 ms / 1.48 ms
8   61.129.147.70   AS4812                    中国 上海   chinatelecom.cn  电信
                                              3.61 ms
    61.129.147.194  AS4812                    中国 上海 上海  chinatelecom.cn 
                                              8.09 ms
    61.129.147.198  AS4812                    中国 上海   chinatelecom.cn  电信
                                              7.89 ms
9   61.129.146.197  AS4812                    中国 上海 上海  chinatelecom.cn 
                                              9.48 ms / 6.66 ms / 4.32 ms
10  101.95.89.62    AS4812   [CHINANET-SH]    中国 上海   chinatelecom.cn  电信
                                              2.64 ms / 8.06 ms / 4.76 ms
11  101.95.88.21    AS4812   [CHINANET-SH]    中国 上海   chinatelecom.cn  电信
                                              * ms / * ms / 2.80 ms
12  *
13  59.43.39.210    *        [CN2-BackBone]   中国 上海   chinatelecom.cn  电信
                                              * ms / 54.15 ms / 54.68 ms
14  59.43.183.82    *        [CN2-BackBone]   中国 香港  X-F chinatelecom.cn  电信
                                              40.65 ms / 29.38 ms / 28.92 ms
15  203.131.241.69  AS2914   [NTT-GLOBAL]     中国 香港   gin.ntt.net 
                                              29.75 ms / 29.55 ms / 29.50 ms
16  203.131.250.82  AS2914   [NTT-GLOBAL]     中国 香港   gin.ntt.net 
                                              29.94 ms / 29.94 ms / 29.97 ms
17  34.80.25.50     AS396982                  中国 台湾 台北  google.com 
    50.25.80.34.bc.googleusercontent.com      43.58 ms / 42.15 ms / 42.19 ms
```

## 日本

到谷歌 GCP 日本绕港：

```
traceroute to 104.198.91.239, 30 hops max, 52 bytes payload, ICMP mode
1   10.0.0.254      *                         RFC1918          
                                              0.20 ms / 0.15 ms / 0.20 ms
2   180.169.18.161  AS4812   [CHINANET-SH]    中国 上海市  黄浦 chinatelecom.cn  电信
                                              1.55 ms / 1.37 ms / 1.41 ms
3   172.16.0.2      *                         RFC1918          
                                              3.11 ms / 2.08 ms / 2.17 ms
4   203.156.240.90  AS4812                    中国 上海市   chinatelecom.cn  电信
                                              4.65 ms / * ms / * ms
5   10.200.200.5    *                         RFC1918          
                                              4.47 ms / 14.44 ms / 5.38 ms
6   180.169.17.165  AS4812   [CHINANET-SH]    中国 上海 上海  chinatelecom.cn 
                                              2.31 ms / 1.62 ms / 1.74 ms
7   58.40.245.25    AS4812                    中国 上海  奉贤区 chinatelecom.cn  电信
                                              2.04 ms / 1.59 ms / 1.62 ms
8   61.129.146.66   AS4812                    中国 上海   chinatelecom.cn  电信
                                              2.00 ms
    61.129.146.198  AS4812                    中国 上海   chinatelecom.cn  电信
                                              1.95 ms
    61.129.146.70   AS4812                    中国 上海 上海  chinatelecom.cn 
                                              4.25 ms
9   *
10  101.95.89.46    AS4812   [CHINANET-SH]    中国 上海   chinatelecom.cn  电信
                                              103.18 ms / * ms / * ms
11  *
12  *
13  *
14  59.43.188.230   *        [CN2-BackBone]   中国 香港   chinatelecom.cn  电信
                                              30.33 ms / 30.39 ms / 29.95 ms
15  203.131.241.69  AS2914   [NTT-GLOBAL]     中国 香港   gin.ntt.net 
    xe-2-5-3-1.a00.chwahk03.hk.bb.gin.ntt.net   27.07 ms / 27.28 ms / 27.03 ms
16  203.131.250.82  AS2914   [NTT-GLOBAL]     中国 香港   gin.ntt.net 
                                              27.35 ms / 27.32 ms / 27.32 ms
17  104.198.91.239  AS396982 [GOOGLE-CLOUD]   日本 东京都 东京  google.com 
    239.91.198.104.bc.googleusercontent.com   60.53 ms / 58.57 ms / 58.54 ms
```

到亚马逊 AWS 东京绕港：

```
traceroute to 35.74.182.183, 30 hops max, 52 bytes payload, ICMP mode
1   10.0.0.254      *                         RFC1918          
                                              0.16 ms / 0.13 ms / 0.20 ms
2   180.169.18.161  AS4812   [CHINANET-SH]    中国 上海市  黄浦 chinatelecom.cn  电信
                                              1.69 ms / 1.36 ms / 1.29 ms
3   172.16.0.2      *                         RFC1918          
                                              3.25 ms / 1.95 ms / 2.24 ms
4   *
5   10.200.200.5    *                         RFC1918          
                                              3.76 ms / 3.87 ms / 20.07 ms
6   180.169.17.165  AS4812   [CHINANET-SH]    中国 上海 上海  chinatelecom.cn 
                                              1.67 ms / 1.50 ms / 1.66 ms
7   58.40.245.25    AS4812                    中国 上海  奉贤区 chinatelecom.cn  电信
                                              1.93 ms / 1.57 ms / 1.59 ms
8   61.129.146.66   AS4812                    中国 上海   chinatelecom.cn  电信
                                              2.05 ms
    61.129.147.66   AS4812                    中国 上海   chinatelecom.cn  电信
                                              16.56 ms
    61.129.147.198  AS4812                    中国 上海   chinatelecom.cn  电信
                                              5.46 ms
9   101.95.89.45    AS4812   [CHINANET-SH]    中国 上海   chinatelecom.cn  电信
                                              10.21 ms / * ms / * ms
10  101.95.89.98    AS4812   [CHINANET-SH]    中国 上海   chinatelecom.cn  电信
                                              107.59 ms / * ms / * ms
11  101.95.88.205   AS4812   [CHINANET-SH]    中国 上海   chinatelecom.cn  电信
                                              7.72 ms / 4.97 ms / 10.50 ms
12  59.43.138.46    *        [CN2-BackBone]   中国 上海  C-I chinatelecom.cn  电信
                                              * ms / 3.49 ms / 3.50 ms
13  *
14  59.43.248.241   *        [CN2-Global]     中国 香港   chinatelecom.cn  电信
                                              33.85 ms / 41.58 ms / 32.32 ms
15  *
16  *
17  *
18  *
19  *
20  *
21  *
22  *
23  *
24  *
25  *
26  *
27  *
28  *
29  *
30  *
```

到微软 Azure 日本绕港：

```
traceroute to 20.210.115.182, 30 hops max, 52 bytes payload, ICMP mode
1   10.0.0.254      *                         RFC1918          
                                              0.27 ms / 0.27 ms / 0.24 ms
2   180.169.18.161  AS4812   [CHINANET-SH]    中国 上海市  黄浦 chinatelecom.cn  电信
                                              1.54 ms / 1.35 ms / 2.52 ms
3   172.16.0.2      *                         RFC1918          
                                              2.99 ms / 2.23 ms / 2.28 ms
4   *
5   10.200.200.5    *                         RFC1918          
                                              4.11 ms / 10.65 ms / 5.26 ms
6   180.169.17.165  AS4812   [CHINANET-SH]    中国 上海 上海  chinatelecom.cn 
                                              1.64 ms / 17.00 ms / 1.72 ms
7   58.40.245.25    AS4812                    中国 上海  奉贤区 chinatelecom.cn  电信
                                              1.96 ms / 1.50 ms / 1.49 ms
8   61.129.146.70   AS4812                    中国 上海 上海  chinatelecom.cn 
                                              * ms / * ms / 102.53 ms
9   101.95.89.41    AS4812   [CHINANET-SH]    中国 上海   chinatelecom.cn  电信
                                              * ms / 53.67 ms
    101.95.89.33    AS4812   [CHINANET-SH]    中国 上海   chinatelecom.cn  电信
                                              53.91 ms
10  101.95.89.46    AS4812   [CHINANET-SH]    中国 上海   chinatelecom.cn  电信
                                              2.69 ms / * ms / * ms
11  *
12  59.43.22.18     *        [CN2-BackBone]   中国 上海  C-I chinatelecom.cn  电信
                                              53.57 ms / * ms / * ms
13  *
14  59.43.183.78    *        [CN2-BackBone]   中国 香港   chinatelecom.cn  电信
                                              32.39 ms / 32.25 ms / 32.20 ms
15  63.218.211.9    AS3491   [PCCW-BACKBONE]  中国 香港   pccwglobal.com 
    te0-1-0-18.br03.hkg15.as3491.net          32.01 ms / 32.22 ms / 32.22 ms
16  63.218.174.122  AS3491   [PCCW-BACKBONE]  中国 香港   pccwglobal.com 
    BE41.br04.hkg12.as3491.net                133.05 ms / * ms / * ms
17  63.216.176.146  AS3491                    中国 香港   pccwglobal.com 
    63-216-176-146.static.as3491.net          66.15 ms / 66.54 ms / 67.76 ms
18  104.44.42.190   AS8075   [MSFT]           中国 香港   microsoft.com 
    ae27-0.icr02.hkg20.ntwk.msn.net           * ms / 66.06 ms / * ms
19  104.44.11.147   AS8075   [MSFT]           中国 香港   microsoft.com 
    be-122-0.ibr02.hkg20.ntwk.msn.net         57.82 ms / 57.26 ms / 57.12 ms
20  104.44.30.134   AS8075   [MSFT]           印度 马哈拉施特拉邦 孟买  microsoft.com 
    be-7-0.ibr03.bom02.ntwk.msn.net           57.87 ms / 58.46 ms / 58.54 ms
21  104.44.30.226   AS8075   [MSFT]           日本 东京都 东京  microsoft.com 
    be-3-0.ibr02.tyo31.ntwk.msn.net           57.20 ms / 57.12 ms / 57.36 ms
22  104.44.20.50    AS8075   [MSFT]           日本 东京都 东京  microsoft.com 
    ae122-0.icr02.tyo31.ntwk.msn.net          57.06 ms / 57.11 ms / 57.19 ms
23  *
24  *
25  *
26  *
27  *
28  *
29  *
30  *
```

到阿里云日本绕港：

```
traceroute to 47.74.25.86, 30 hops max, 52 bytes payload, ICMP mode
1   10.0.0.254      *                         RFC1918          
                                              0.29 ms / 0.17 ms / 0.18 ms
2   180.169.18.161  AS4812   [CHINANET-SH]    中国 上海市  黄浦 chinatelecom.cn  电信
                                              1.41 ms / 1.37 ms / 1.27 ms
3   172.16.0.2      *                         RFC1918          
                                              2.74 ms / 1.90 ms / 2.33 ms
4   *
5   10.200.200.5    *                         RFC1918          
                                              7.94 ms / 4.68 ms / 3.59 ms
6   180.169.17.165  AS4812   [CHINANET-SH]    中国 上海 上海  chinatelecom.cn 
                                              1.84 ms / 1.74 ms / 2.20 ms
7   58.40.245.25    AS4812                    中国 上海  奉贤区 chinatelecom.cn  电信
                                              1.92 ms / 2.28 ms / 1.60 ms
8   61.129.147.58   AS4812                    中国 上海 上海  chinatelecom.cn 
                                              1.66 ms
    61.129.147.190  AS4812                    中国 上海 上海  chinatelecom.cn 
                                              1.56 ms
    61.129.146.190  AS4812                    中国 上海 上海  chinatelecom.cn 
                                              1.76 ms
9   *
10  101.95.89.42    AS4812   [CHINANET-SH]    中国 上海   chinatelecom.cn  电信
                                              4.00 ms / 2.38 ms / 2.48 ms
11  61.152.24.181   AS4812   [CHINANET-SH]    中国 上海   chinatelecom.cn  电信
                                              5.54 ms / 2.78 ms / 7.80 ms
12  *
13  59.43.39.102    *        [CN2-BackBone]   中国 上海   chinatelecom.cn  电信
                                              * ms / * ms / 103.58 ms
14  59.43.183.82    *        [CN2-BackBone]   中国 香港  X-F chinatelecom.cn  电信
                                              28.40 ms / 28.97 ms / 28.33 ms
15  203.131.241.65  AS2914   [NTT-GLOBAL]     中国 香港   gin.ntt.net 
    xe-2-5-3-2.a01.chwahk03.hk.bb.gin.ntt.net   36.27 ms / 35.93 ms / 29.00 ms
16  129.250.2.188   AS2914   [NTT-BACKBONE]   中国 香港   gin.ntt.net 
    ae-7.r26.tkokhk01.hk.bb.gin.ntt.net       * ms / 80.90 ms / 81.37 ms
17  *
18  129.250.2.42    AS2914   [NTT-BACKBONE]   日本 大阪府 大阪  gin.ntt.net 
    ae-4.r26.osakjp02.jp.bb.gin.ntt.net       * ms / * ms / 123.49 ms
19  *
20  129.250.7.14    AS2914   [NTT-BACKBONE]   日本 东京都 东京  gin.ntt.net 
    ae-0.a00.tokyjp09.jp.bb.gin.ntt.net       62.85 ms / 62.84 ms / 62.76 ms
21  *
22  *
23  *
24  *
25  47.74.25.86     AS45102                   日本 东京都 东京  alibabagroup.com 
                                              64.11 ms / 64.16 ms / 64.07 ms
```

## 美国

到美西谷歌 GCP 绕港：

```
traceroute to 34.102.85.154, 30 hops max, 52 bytes payload, ICMP mode
1   10.0.0.254      *                         RFC1918          
                                              0.20 ms / 0.16 ms / 0.16 ms
2   180.169.18.161  AS4812   [CHINANET-SH]    中国 上海市  黄浦 chinatelecom.cn  电信
                                              1.38 ms / 1.35 ms / 1.32 ms
3   172.16.0.2      *                         RFC1918          
                                              2.89 ms / 2.01 ms / 2.38 ms
4   *
5   10.200.200.5    *                         RFC1918          
                                              6.49 ms / 4.03 ms / 5.22 ms
6   180.169.17.165  AS4812   [CHINANET-SH]    中国 上海 上海  chinatelecom.cn 
                                              1.98 ms / 1.67 ms / 1.84 ms
7   58.40.245.25    AS4812                    中国 上海  奉贤区 chinatelecom.cn  电信
                                              2.29 ms / 1.98 ms / 1.93 ms
8   61.129.147.70   AS4812                    中国 上海   chinatelecom.cn  电信
                                              1.88 ms
    61.129.146.198  AS4812                    中国 上海   chinatelecom.cn  电信
                                              2.43 ms
    61.129.147.194  AS4812                    中国 上海 上海  chinatelecom.cn 
                                              1.84 ms
9   61.129.146.197  AS4812                    中国 上海 上海  chinatelecom.cn 
                                              11.10 ms / 8.44 ms / 5.58 ms
10  101.95.89.50    AS4812   [CHINANET-SH]    中国 上海   chinatelecom.cn  电信
                                              7.57 ms / 4.51 ms / 10.05 ms
11  101.95.88.21    AS4812   [CHINANET-SH]    中国 上海   chinatelecom.cn  电信
                                              53.26 ms / * ms / * ms
12  59.43.159.98    *        [CN2-BackBone]   中国 上海  C-I chinatelecom.cn  电信
                                              53.56 ms / 53.43 ms / * ms
13  59.43.39.190    *        [CN2-BackBone]   中国 上海  I-X chinatelecom.cn  电信
                                              2.65 ms / * ms / * ms
14  59.43.249.29    *        [CN2-Global]     中国 香港   chinatelecom.cn  电信
                                              26.78 ms / 27.50 ms / 27.48 ms
15  203.131.241.69  AS2914   [NTT-GLOBAL]     中国 香港   gin.ntt.net 
    xe-2-5-3-1.a00.chwahk03.hk.bb.gin.ntt.net   27.43 ms / 27.31 ms / 27.06 ms
16  203.131.250.82  AS2914   [NTT-GLOBAL]     中国 香港   gin.ntt.net 
                                              27.36 ms / 27.47 ms / 30.03 ms
17  34.102.85.154   AS396982                  美国 加利福尼亚州 洛杉矶  google.com 
    154.85.102.34.bc.googleusercontent.com    155.99 ms / 154.01 ms / 154.02 ms
```

到美西亚马逊 AWS 直连（终于有走上海的了）：

```
traceroute to 54.215.39.119, 30 hops max, 52 bytes payload, ICMP mode
1   10.0.0.254      *                         RFC1918          
                                              0.20 ms / 0.16 ms / 0.20 ms
2   180.169.18.161  AS4812   [CHINANET-SH]    中国 上海市  黄浦 chinatelecom.cn  电信
                                              1.51 ms / 1.26 ms / 3.06 ms
3   172.16.0.2      *                         RFC1918          
                                              3.05 ms / 2.83 ms / 2.94 ms
4   *
5   10.200.200.5    *                         RFC1918          
                                              4.06 ms / 3.95 ms / 8.84 ms
6   180.169.17.165  AS4812   [CHINANET-SH]    中国 上海 上海  chinatelecom.cn 
                                              4.52 ms / 4.07 ms / 2.37 ms
7   58.40.245.25    AS4812                    中国 上海  奉贤区 chinatelecom.cn  电信
                                              14.68 ms / 16.82 ms / 31.42 ms
8   61.129.146.198  AS4812                    中国 上海   chinatelecom.cn  电信
                                              47.29 ms
    61.129.146.70   AS4812                    中国 上海 上海  chinatelecom.cn 
                                              39.51 ms
    61.129.147.194  AS4812                    中国 上海 上海  chinatelecom.cn 
                                              26.04 ms
9   101.95.89.33    AS4812   [CHINANET-SH]    中国 上海   chinatelecom.cn  电信
                                              7.82 ms / * ms / * ms
10  101.95.89.42    AS4812   [CHINANET-SH]    中国 上海   chinatelecom.cn  电信
                                              52.86 ms / * ms / * ms
11  *
12  59.43.22.18     *        [CN2-BackBone]   中国 上海  C-I chinatelecom.cn  电信
                                              104.15 ms / * ms / * ms
13  *
14  59.43.182.145   *        [CN2-BackBone]   美国 加利福尼亚 圣何塞  chinatelecom.cn  电信
                                              139.08 ms / 138.62 ms / 138.73 ms
15  80.239.132.157  AS1299                    美国 加利福尼亚 圣何塞  arelion.com 
    sjo-b23-link.ip.twelve99.net              145.61 ms / 144.99 ms / 145.67 ms
16  *
17  *
18  *
19  *
20  *
21  *
22  *
23  *
24  *
25  *
26  *
27  *
28  *
29  *
30  *
```

到美西微软 Azure绕港：

```
traceroute to 104.42.170.197, 30 hops max, 52 bytes payload, ICMP mode
1   10.0.0.254      *                         RFC1918          
                                              0.28 ms / 0.17 ms / 0.29 ms
2   180.169.18.161  AS4812   [CHINANET-SH]    中国 上海市  黄浦 chinatelecom.cn  电信
                                              1.54 ms / 1.26 ms / 16.74 ms
3   172.16.0.2      *                         RFC1918          
                                              3.08 ms / 2.91 ms / 3.13 ms
4   *
5   10.200.200.5    *                         RFC1918          
                                              3.37 ms / 5.25 ms / 3.33 ms
6   180.169.17.165  AS4812   [CHINANET-SH]    中国 上海 上海  chinatelecom.cn 
                                              1.42 ms / 3.04 ms / 1.59 ms
7   58.40.245.25    AS4812                    中国 上海  奉贤区 chinatelecom.cn  电信
                                              1.84 ms / 1.50 ms / 1.51 ms
8   61.129.147.62   AS4812                    中国 上海 上海  chinatelecom.cn 
                                              1.54 ms
    61.129.146.190  AS4812                    中国 上海 上海  chinatelecom.cn 
                                              8.01 ms
    61.129.147.186  AS4812                    中国 上海 上海  chinatelecom.cn 
                                              6.98 ms
9   61.129.146.189  AS4812                    中国 上海 上海  chinatelecom.cn 
                                              6.67 ms / 3.75 ms / 8.72 ms
10  101.95.89.50    AS4812   [CHINANET-SH]    中国 上海   chinatelecom.cn  电信
                                              7.90 ms / 4.74 ms / 9.79 ms
11  101.95.88.41    AS4812   [CHINANET-SH]    中国 上海   chinatelecom.cn  电信
                                              2.69 ms / 7.67 ms / 4.81 ms
12  59.43.46.78     *        [CN2-BackBone]   中国 广东 广州  chinatelecom.cn  电信
                                              24.67 ms / 24.65 ms / 24.64 ms
13  59.43.130.150   *        [CN2-BackBone]   中国 广东 广州 C-I chinatelecom.cn  电信
                                              * ms / * ms / 134.51 ms
14  59.43.250.110   *        [CN2-Global]     中国 广东 广州  chinatelecom.cn  电信
                                              * ms / * ms / 28.35 ms
15  203.22.178.205  *        [CTG-CN]         中国 香港   CTGNet
    CT163.CN.HKG.CTGNet                       30.55 ms / 31.81 ms / 31.03 ms
16  63.216.142.9    AS3491                    中国 香港   pccwglobal.com 
    hu0-0-0-22.br05.hkg15.as3491.net          * ms / * ms / 30.30 ms
17  63.218.174.134  AS3491   [PCCW-BACKBONE]  中国 香港   pccwglobal.com 
    BE42.br04.hkg12.as3491.net                * ms / 81.02 ms / 81.55 ms
18  63.216.176.146  AS3491                    中国 香港   pccwglobal.com 
    63-216-176-146.static.as3491.net          64.52 ms / 67.07 ms / 65.12 ms
19  104.44.42.190   AS8075   [MSFT]           中国 香港   microsoft.com 
    ae27-0.icr02.hkg20.ntwk.msn.net           64.17 ms / 64.44 ms / 76.16 ms
20  104.44.11.147   AS8075   [MSFT]           中国 香港   microsoft.com 
    be-122-0.ibr02.hkg20.ntwk.msn.net         161.92 ms / 161.97 ms / 161.99 ms
21  104.44.17.102   AS8075   [MSFT]           日本 东京都 东京  microsoft.com 
    be-5-0.ibr02.tyo31.ntwk.msn.net           162.90 ms / 285.77 ms / 241.11 ms
22  104.44.28.160   AS8075   [MSFT]           阿联酋 迪拜酋长国 迪拜市  microsoft.com 
    be-10-0.ibr01.dxb20.ntwk.msn.net          162.10 ms / 162.81 ms / 163.31 ms
23  104.44.19.85    AS8075   [MSFT]           美国 俄勒冈 波特兰  microsoft.com 
    be-5-0.ibr02.pdx30.ntwk.msn.net           164.91 ms / 163.21 ms / 162.25 ms
24  104.44.7.69     AS8075   [MSFT]           埃及 马特鲁省 العلمين  microsoft.com 
    be-7-0.ibr03.dbb.ntwk.msn.net             161.91 ms / 162.27 ms / 162.01 ms
25  104.44.23.71    AS8075   [MSFT]           美国 加利福尼亚 旧金山  microsoft.com 
    ae144-0.icr03.by21.ntwk.msn.net           162.37 ms / 162.27 ms / 162.24 ms
26  *
27  *
28  *
29  *
30  *
```

到阿里云美西走上海出但是绕新加坡：

```
traceroute to 47.251.20.186, 30 hops max, 52 bytes payload, ICMP mode
1   10.0.0.254      *                         RFC1918          
                                              0.19 ms / 0.15 ms / 0.18 ms
2   180.169.18.161  AS4812   [CHINANET-SH]    中国 上海市  黄浦 chinatelecom.cn  电信
                                              2.26 ms / 1.20 ms / 1.30 ms
3   172.16.0.2      *                         RFC1918          
                                              3.98 ms / 2.41 ms / 2.09 ms
4   *
5   10.200.200.5    *                         RFC1918          
                                              4.61 ms / 3.44 ms / 3.34 ms
6   180.169.17.165  AS4812   [CHINANET-SH]    中国 上海 上海  chinatelecom.cn 
                                              1.79 ms / 1.74 ms / 1.71 ms
7   58.40.245.25    AS4812                    中国 上海  奉贤区 chinatelecom.cn  电信
                                              1.98 ms / 1.58 ms / 1.52 ms
8   61.129.147.62   AS4812                    中国 上海 上海  chinatelecom.cn 
                                              9.77 ms
    61.129.147.186  AS4812                    中国 上海 上海  chinatelecom.cn 
                                              9.22 ms
    61.129.146.58   AS4812                    中国 上海 上海  chinatelecom.cn 
                                              1.73 ms
9   101.95.89.37    AS4812   [CHINANET-SH]    中国 上海   chinatelecom.cn  电信
                                              70.06 ms / * ms / * ms
10  101.95.89.38    AS4812   [CHINANET-SH]    中国 上海   chinatelecom.cn  电信
                                              2.96 ms / 53.24 ms / * ms
11  101.95.88.33    AS4812   [CHINANET-SH]    中国 上海   chinatelecom.cn  电信
                                              6.33 ms / 3.74 ms / 8.62 ms
12  *
13  *
14  59.43.249.193   *        [CN2-Global]     新加坡    chinatelecom.cn  电信
                                              65.34 ms / 65.12 ms / 65.13 ms
15  210.57.30.129   AS4637   [TELSTRA_CHINATELECOM] 新加坡    telstraglobal.com 
                                              65.21 ms / 65.11 ms / 65.41 ms
16  180.87.54.6     AS6453   [TATA-COMMUNICATIONS] 新加坡    tatacommunications.com 
                                              63.46 ms / 63.12 ms / 63.26 ms
17  180.87.108.80   AS6453   [TATA-COMMUNICATIONS] 新加坡    tatacommunications.com 
    if-be-18-2.ecore2.esin4-singapore.as6453.net   229.75 ms / * ms / * ms
18  63.243.180.131  AS6453                    新加坡    tatacommunications.com 
                                              179.73 ms / 180.22 ms / 179.64 ms
19  *
20  116.0.74.22     AS6453   [TATA-COMMUNICATIONS] 日本 千叶   tatacommunications.com 
    if-bundle-2-2.qcore1.kv8-chiba.as6453.net   * ms / * ms / 229.72 ms
21  209.58.86.144   AS6453   [TATAC-ARIN]     美国 加利福尼亚 圣克拉拉  tatacommunications.com 
    if-ae-28-5.tcore2.sv1-santaclara.as6453.net   180.23 ms / 180.24 ms / 180.38 ms
22  *
23  66.198.101.129  AS6453                    美国 加利福尼亚 圣何塞  tatacommunications.com 
    if-bundle-2-2.qcore2.sqn-sanjose.as6453.net   230.43 ms / * ms / * ms
24  *
25  *
26  *
27  *
28  47.251.20.186   AS45102                   美国 加利福尼亚州 圣克拉拉  alibabagroup.com 
                                              183.78 ms / 183.72 ms / 183.73 ms
```


## 总结

食之无味。只适合去香港方向。其他方向不如直接买优化线路的 VPS。