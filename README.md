# Debian_Reinstall
由于Vicer删除hostloc论坛账号，自己的博客也开始维护，故在此做备份。
## 安装Debian 10
```
bash <(wget --no-check-certificate -qO- 'https://moeclub.org/attachment/LinuxShell/InstallNET.sh') -d 10 -v 64 -a
```
## Oracle安装Debian 10
```
bash <(wget --no-check-certificate -qO- 'https://moeclub.org/attachment/LinuxShell/InstallNET.sh') -d 10 -v 64 -a -firmware
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
