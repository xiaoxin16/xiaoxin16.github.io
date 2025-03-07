---
title: 在ubuntu22中安装网盘工具nextcloud
author: xyh
date: 2024-04-07 13:38:00 +0800
categories: [学习, 技术, 网盘]
tags: [网盘, nextcloud]
---

[toc]{type: "ul", level: [1,2,3]}

**安装思路**
在主机搭建VMware虚拟机，并安装ubuntu22虚拟系统
1. 安装docker环境
2. docker-mysql
3. docker-onlyoffice
4. apache2
5. nextcloud

# ubuntu22 install
```
略，VMware中安装
```

##  挂载数据盘并开机挂载
1. 查看新盘符
```
fdisk -l
```
2. 分区（暂不需要）
3. 格式化硬盘文件系统
```
mkfs -t ext4 /dev/sdb
```
4. 挂载硬盘
```
# 创建要挂载的文件夹
mkdir /data
# 挂载硬盘到该文件夹上
mount /dev/sdb /data
# 开机加载
# blkid查看uuid
# 进入 fstab 修改配置
vim /etc/fstab
# 在最后面加入指定信息 fdisk -l 查看
UUID=67E91005-EB18-4E24-8410-EB9A1C2E3882 /data ext4 defaults 0 0
# 取消挂载
umount /dev/sde
# 查看
df -hT
```

# docker安装[--]
```
apt upgrade
apt install apt-transport-https ca-certificates curl software-properties-common gnupg lsb-release
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
apt update
apt install docker-ce docker-ce-cli containerd.io docker-compose-plugin
systemctl status docker
systemctl start docker
systemctl enable docker
```
# mysql 源码安装
```
docker pull mysql:latest
```


# onlyoffice安装
```
docker pull onlyoffice/documentserver:7.1.1
docker run -i -t -d --restart=always --name onlyoffice -v /data/onlyoffice/DocumentServer/data:/var/www/onlyoffice/Data -v /data/onlyoffice/DocumentServer/logs:/var/log/onlyoffice onlyoffice/documentserver:7.1.1
```


# apache2+mysql
https://docs.nextcloud.com/server/latest/admin_manual/installation/example_ubuntu.html
```
apt install apache2 mariadb-server libapache2-mod-php php-gd php-mysql \
php-curl php-mbstring php-intl php-gmp php-bcmath php-xml php-imagick php-zip

CREATE USER 'nc'@'%' IDENTIFIED BY 'admin123';
CREATE DATABASE IF NOT EXISTS nextcloud CHARACTER SET utf8mb4 COLLATE utf8mb4_general_ci;
GRANT ALL PRIVILEGES ON nextcloud.* TO 'nc'@'%';
FLUSH PRIVILEGES;
```
https://vegastack.com/tutorials/how-to-install-nextcloud-on-ubuntu-22-04-with-apache-lamp-stack/
1. 下载源码
2. 修改权限
```
chown -R www-data:www-data /var/www/nextcloud
systemctl restart apache2
```

3. 管理
- admin/admin123