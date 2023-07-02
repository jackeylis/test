# test1
软件测试笔记
## Linux常用指令
rpm -qi 软件    查看软件具体信息

rpm -qf  文件路径  逆向查找

rpm -ql 软件（配合grpe使用）  查询文件位置
```

##### 卸载

```
rpm -e 卸载
rpm -e 软件 --nodeps 强制删除
```

##### 安装质量

```
rpm -ivh  安装包全程称
-安装 安装
-详细提示
-hash 进度条
```



##### 挂载

```
安装火狐
1.将CentOS7挂在在media下 mount /dev/cdrom /media
2.在 /media下查找到CentOS7的挂在文件
3.检索火狐安装包
4.将安装包复制到 /opt路径中
5.安装火狐  rpm -ivh1.CentOS7挂在media下 mount /dev/cdrom
```

```
从YUM端下载MYSQL
1.关闭防火墙
systemctl stop firewalld.service   一次关闭
systemctl 禁用 firewalld.service 禁止开机启动

2.快照
3.卸载MYSQL同源的mariadb
rpm -qa |grep mariadb      检查
yum remove mariadb-libs  卸载


3.配置 wget
yum install wget   配置环境安装包

4.前往 cd /usr/local/src路径存放安装包

5.从wget端下载MYsql
wget http://dev.mysql.com/get/mysql57-community-release-el7-11.noarch.rpm

6.运行安装包
rpm -ivh mysql57-community-release-el7-11.noarch.rpm

7.安装密钥
rpm --import https://repo.mysql.com/RPM-GPG-KEY-mysql-2022

8.yum源中下载安装包
yum install mysql-server

9.启动服务
systemctl start mysqld 启动服务（单次启动）
systemctl enable mysqld 开机启动

10.查询默认密码
grep 'temporary password' /var/log/mysqld.log
OCyB.VdjZ6Qz

11.修改密码
set password for root@localhost = password'123456';

12.重置密码策略
修改etc文件  /etc/my.cnf

13.跳过验证
在mysqld下添加 skip-grant-tables[]

14.重启Mysql服务器
systemctl restart mysqld

15.下载mysql的依赖包
yum install mysql-devel

16.重复12、13步，把 skip-grant-tables 删掉并保存

17.重复14步 重启mysql服务器

18.登录mysql 
mysql -u -root -p
登陆时输入密码为不可见，密码已修改为123456

19.验证能否使用
show databases;
```



#### 硬盘

##### 挂载硬盘

```
1.虚拟机 -设置-添加硬盘-2G

2. 硬盘分区
   fdisk /dev/sdb (检查名字有可能不一样）
   m ——n——p——1——回车——回车

3.格式化
mkfs -t ext4 /dev/sdb
出现无论如何都要进行 输入y 回车


4.创建挂在目录
通常创建位置要在 dev路径下

5.开始挂载（单次挂载）
mount 硬盘路径 挂载路径
取消挂在 umount 硬盘路径

6.永久挂载
```

### shell脚本

```
sh：shell脚本执行器  使用方法：sh 脚本地址（/home/shell/myshell.sh）
chmod u+x myshell.sh：赋予脚本权限可执行脚本
chmod u-x myshell.sh：删除权限无法直接执行脚本
当没有权限时可以使用sh脚本执行器使用
```
