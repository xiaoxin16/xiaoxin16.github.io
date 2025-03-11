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

# 获得管理员信息 以下两个不同版本，新版本也有随机生成和手动设置
# 低于v3.25.0版本
.\alist.exe admin

# 高于v3.25.0版本
# 随机生成一个密码
.\alist.exe admin random
# 手动设置一个密码 `NEW_PASSWORD`是指你需要设置的密码
.\alist.exe admin set 123456
```

## 恢复TasksModule
## xx

# 
# 
# 