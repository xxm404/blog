---
title: "CurlLatency"
date: 2020-02-16T17:51:11+08:00
draft: false
toc: false
images:
tags: 
  - curl, tool
---

## Curl 分析请求耗时

`$ curl -w "@curl-latency.txt" -o /dev/null -s http://target-server`

```bash
# The contents of curl-latency.txt
    time_namelookup:  %{time_namelookup}\n		# DNS 域名解析消耗时间
       time_connect:  %{time_connect}\n				# TCP 连接建立时间
    time_appconnect:  %{time_appconnect}\n		# SSL/SSH 完成连接和握手消耗时间
   time_pretransfer:  %{time_pretransfer}\n		# 从请求开始到响应开始传输的时间
      time_redirect:  %{time_redirect}\n			# 
 time_starttransfer:  %{time_starttransfer}\n	# 从请求开始到第一个字节将要传输的时间
                    ----------\n
         time_total:  %{time_total}\n					# 总耗时
# TCP 连接时间 	pretransfter - namelookup
# Server handle 时间 starttransfter - pretransfer
# 内容传输时间 total - starttransfer
```

Simple output:

```bash
$ curl -w "@curl-latency.txt" -o /dev/null -s http://192.0.2.1/api-endpoint
    time_namelookup:  0.000035
       time_connect:  0.000364
    time_appconnect:  0.000000
   time_pretransfer:  0.000401
      time_redirect:  0.000000
 time_starttransfer:  0.001701
                    ----------
         time_total:  0.001727
```

