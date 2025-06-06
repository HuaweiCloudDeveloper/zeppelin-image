# Jaeger部署指南

## ‌一、环境准备

### 系统配置
> -  服务器：鲲鹏服务器
> -  操作系统：Huawei Cloud EulerOS 2.0 64bit
> - CPU: 2vCPUs 或更高
> - RAM: 4GB 或更大
> - Disk: 至少 40GB

### 前置条件

> -  JDK：jdk1.8

## ‌二、下载安装

### 1.下载
```bash
# 从官网下载二进制包并解压至目标目录 
wget https://dlcdn.apache.org/zeppelin/zeppelin-0.12.0/zeppelin-0.12.0.bin-all.tgz  
tar -zxvf zeppelin-0.12.0-bin-all.tgz -C /opt 
```
### 2.关键配置文件修改
修改 conf/zeppelin-site.xml，设置服务端口（默认 8080）,若端口冲突，可调整为其他值（如 8888）‌。

```xml
<property>  
    <name>zeppelin.server.port</name>  
    <value>8080</value>  
</property> 
```
‌绑定地址:修改 zeppelin.server.addr 为 0.0.0.0，允许远程访问‌。

## 三、服务启动
服务‌‌启动
```bash
cd /opt/zeppelin-0.12.1-bin-all  
./bin/zeppelin-daemon.sh start  
```
