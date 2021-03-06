1. 开启端口
```shell
vim /etc/sysconfig/iptables-config

# 将这行添加到iptables文件中
-A INPUT -p tcp -m state --state NEW -m tcp --dport 3306 -j ACCEPT
```
2. 查看catalina日志
```shell
tail -f catalina.sh
```
3. 查看Tomcat进程
```shell
ps -ef | grep tomcat
```
4. 禁用防火墙
```shell
# 关闭防火墙
systemctl stop firewalld
# 立即生效
setenforce 0
# 关闭开机自启
systemctl disable firewalld
```
5. 开放防火墙端口(上面禁用防火墙不安全)
```shell
## Add
firewall-cmd --permanent --zone=public --add-port=8080/tcp
## Reload
firewall-cmd --reload
## 检查是否生效
firewall-cmd --zone=public --query-port=8080/tcp
```
6. 查看端口被哪个进程占用
```shell
## 安装lsof
yum install lsof -y
## 查看端口占用情况
lsof -i:端口号

```
7. 删除文件夹
```shell
# r 递归删除，f 强行删除
rm -rf 文件夹
```
8. 拷贝文件夹
```shell
# r 递归拷贝，否则如果存在子文件夹，则会报错 omitting directory
cp -r a dirA dirB
```
9. 查看CentOS版本号
```shell
cat /etc/redhat-release
```
10. 找不到make命令
```shell
# 需要安装gcc，执行一下就可以了：
yum -y install gcc automake autoconf libtool make
yum install gcc gcc-c++
```
