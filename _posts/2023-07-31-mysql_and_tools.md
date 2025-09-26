---
title: MYSQL+ALIST+TOOLS
author: xyh
date: 2023-07-31 16:32:00 +0800
categories: [学习, 技术]
tags: [MYSQL]
---

[toc]{type: "ul", level: [1,2,3]}

# MYSQL本地部署
ref[https://segmentfault.com/a/1190000043052363]
```
1. 修改配置文件my.ini
2. 添加系统环境变量
3. 管理员运行 mysqld --initialize-insecure --user=mysql
4. 
```

# ALIST
## 安装
参考[https://alist.nn.ci/zh/guide/install/manual.html]
```
# 解压下载的文件，得到可执行文件：
unzip alist-xxxx.zip
# 运行程序
.\alist.exe server

# 获得管理员信息
.\alist.exe admin set 123456
# .\nssm.exe install alist and ...
```
# MITM 代理
mitm[https://blog.csdn.net/JD_MM/article/details/106602701#:~:text=win10%20--%20mitmproxy%E5%AE%89%E8%A3%85%E7%AC%94%E8%AE%B0%201%201%E3%80%81%E5%9C%A8%E5%91%BD%E4%BB%A4%E8%A1%8C%E8%BE%93%E5%85%A5mitmdump%EF%BC%8C%E9%BB%98%E8%AE%A4%E7%9B%91%E5%90%AC8080%E7%AB%AF%E5%8F%A3%EF%BC%8C%E5%BD%93%E5%89%8D%E5%8F%AF%E4%BB%A5%E5%8A%A0-p%E5%8F%82%E6%95%B0%E6%8C%87%E5%AE%9A%E7%AB%AF%E5%8F%A3%202%202%E3%80%81%E8%AE%BE%E7%BD%AE%E4%BB%A3%E7%90%86%EF%BC%8C%E5%B9%B6%E6%89%93%E5%BC%80%E4%BB%A3%E7%90%86%EF%BC%9A,%E6%96%B9%E5%BC%8F%E4%B8%80%EF%BC%9A%E5%8F%AF%E5%9C%A8%E6%B5%8F%E8%A7%88%E5%99%A8%E4%B8%AD%E8%AE%BE%E7%BD%AE%E4%BB%A3%E7%90%86%20%E6%96%B9%E5%BC%8F%E4%BA%8C%EF%BC%9A%E4%B9%9F%E5%8F%AF%E5%9C%A8%E6%9C%AC%E5%9C%B0%E8%AE%BE%E7%BD%AE%E4%BB%A3%E7%90%86%203%203%E3%80%81%E6%B5%8F%E8%A7%88%E5%99%A8%E8%BE%93%E5%85%A5http%3A%2F%2Fmitm.it%2F%E6%A0%B9%E6%8D%AE%E9%9C%80%E8%A6%81%E4%B8%8B%E8%BD%BD%E5%AF%B9%E5%BA%94%E7%9A%84%E8%AF%81%E4%B9%A6%20Windows%E8%AF%81%E4%B9%A6%EF%BC%9Amitmproxy-ca-cert.p12%20Android%E8%AF%81%E4%B9%A6%20%EF%BC%9Amitmproxy-ca-cert.pem]


# 恢复TasksModule
## xx

# 
# 
# 