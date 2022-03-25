# Debian_Reinstall
由于Vicer删除hostloc论坛账号，自己的博客也开始维护，故在此做备份。
## 安装Debian 11
```
bash <(wget --no-check-certificate -qO- 'https://moeclub.org/attachment/LinuxShell/InstallNET.sh') -d 11 -v 64 -a
```
## Oracle安装Debian 11
```
bash <(wget --no-check-certificate -qO- 'https://moeclub.org/attachment/LinuxShell/InstallNET.sh') -d 11 -v 64 -a -firmware
```
## 小内存VPS安装Debian 11
```
bash <(wget --no-check-certificate -qO- 'https://raw.githubusercontent.com/yushum/Debian_Reinstall/master/InstallNET.sh') -d 11 -v 64 -a
```
## 关于debian8源报错

在脚本中可以添加 --mirror 参数切换源。
目前可用的源:
```
--mirror 'http://cpgs.fdcservers.net/debian/'
--mirror 'http://proyectos.uls.edu.sv/debian/'
--mirror 'http://debian.cabletel.com.mk/debian/'
--mirror 'http://komo.padinet.com/debian/'
--mirror 'http://www.debian.uz/debian/'
```
安装debian8 示例:
```
bash InstallNET.sh -d 8 -v 64 -a --mirror 'http://debian.cabletel.com.mk/debian/'
```
安装dd镜像 示例:
```
bash InstallNET.sh -dd "[URL]" --mirror 'http://debian.cabletel.com.mk/debian/'
```

## 确保安装了所需软件:

``` 
#Debian/Ubuntu:
apt-get install -y xz-utils openssl gawk file
 
#RedHat/CentOS:
yum install -y xz openssl gawk file
``` 

## 下载及说明:
``` 
wget --no-check-certificate -qO InstallNET.sh 'https://moeclub.org/attachment/LinuxShell/InstallNET.sh' && chmod +x InstallNET.sh
``` 
```
Usage:
        bash InstallNET.sh      -d/--debian [dist-name]
                                -u/--ubuntu [dist-name]
                                -c/--centos [dist-version]
                                -v/--ver [32/i386|64/amd64]
                                --ip-addr/--ip-gate/--ip-mask
                                -apt/-yum/--mirror
                                -dd/--image
                                -a/-m
 
# dist-name: 发行版本代号
# dist-version: 发行版本号
# -apt/-yum/--mirror : 使用定义镜像
# -a/-m : 询问是否能进入VNC自行操作. -a 为不提示(一般用于全自动安装), -m 为提示.
```

## 使用示例:
```
#使用默认镜像全自动安装
bash InstallNET.sh -d 8 -v 64 -a
bash InstallNET.sh -d 9 -v 64 -a
bash InstallNET.sh -d 10 -v 64 -a
分别表示自动安装Debian 8x64  9x64 10x64
 
#使用自定义镜像全自动安装
bash InstallNET.sh -c 6.9 -v 64 -a --mirror 'http://mirror.centos.org/centos'
 
 
# 以下示例中,将X.X.X.X替换为自己的网络参数.
# --ip-addr :IP Address/IP地址
# --ip-gate :Gateway   /网关
# --ip-mask :Netmask   /子网掩码
 
#使用自定义镜像自定义网络参数全自动安装
#bash InstallNET.sh -u 16.04 -v 64 -a --ip-addr x.x.x.x --ip-gate x.x.x.x --ip-mask x.x.x.x --mirror 'http://archive.ubuntu.com/ubuntu'
 
#使用自定义网络参数全自动dd方式安装
#bash InstallNET.sh --ip-addr x.x.x.x --ip-gate x.x.x.x --ip-mask x.x.x.x -dd 'https://moeclub.org/get-win7embx86-auto'
 
#使用自定义网络参数全自动dd方式安装存储在谷歌网盘中的镜像(调用文件ID的方式)
#bash InstallNET.sh --ip-addr x.x.x.x --ip-gate x.x.x.x --ip-mask x.x.x.x -dd "$(echo "1cqVl2wSGx92UTdhOxU9pW3wJgmvZMT_J" |xargs -n1 bash <(wget --no-check-certificate -qO- 'https://moeclub.org/get-gdlink'))"
 
#使用自定义网络参数全自动dd方式安装存储在谷歌网盘中的镜像
#bash InstallNET.sh --ip-addr x.x.x.x --ip-gate x.x.x.x --ip-mask x.x.x.x -dd "$(echo "https://drive.google.com/open?id=1cqVl2wSGx92UTdhOxU9pW3wJgmvZMT_J" |xargs -n1 bash <(wget --no-check-certificate -qO- 'https://moeclub.org/get-gdlink'))"
```

## 一些可用镜像地址:
```
# 推荐使用带有 /GoogleDrive/<File_ID> 链接, 速度更快.
# 当然也可以使用自己GoogleDrive中储存的镜像,使用方式:
  https://image.moeclub.org/GoogleDrive/<File_ID>
 
# win7emb_x86.tar.gz:
  https://image.moeclub.org/GoogleDrive/1srhylymTjYS-Ky8uLw4R6LCWfAo1F3s7 
  https://image.moeclub.org/win7emb_x86.tar.gz
 
# win8.1emb_x64.tar.gz:
  https://image.moeclub.org/GoogleDrive/1cqVl2wSGx92UTdhOxU9pW3wJgmvZMT_J
  https://image.moeclub.org/win8.1emb_x64.tar.gz
```
