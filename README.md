# test1
软件测试笔记
## Linux常用指令
文件和目录操作：

ls：列出目录内容。
用法：ls [选项] [文件/目录]
常用选项：
-l：以长格式显示文件和目录详细信息。
-a：显示所有文件和目录，包括以开头的隐藏文件。.
cd：切换当前工作目录。
用法：cd [目录路径]
示例： 将当前工作目录切换到 。cd /home/user/Documents/home/user/Documents
pwd：显示当前工作目录的路径。
用法：pwd
mkdir：创建新目录。
用法：mkdir [选项] 目录名
常用选项：
-p：递归创建目录，如果父级目录不存在。
rm：删除文件或目录。
用法：rm [选项] 文件/目录
常用选项：
-r：递归删除目录及其内容。
-f：强制删除，不提示确认。
cp：复制文件或目录。
用法：cp [选项] 源文件/目录 目标文件/目录
常用选项：
-r：递归复制目录及其内容。
-i：在复制前提示确认。
mv：移动或重命名文件或目录。
用法：mv [选项] 源文件/目录 目标文件/目录
常用选项：
-i：在移动前提示确认。
find：按照条件查找文件和目录。
用法：find [路径] [选项] [表达式]
示例： 在 目录下查找所有扩展名为 的文件。find /home/user -name "*.txt"/home/user.txt
文件查看和编辑：

cat：显示文件内容。
用法：cat [文件]
less：按页查看文件内容。
用法：less [文件]
按下空格键翻页，按Q键退出。
head：显示文件开头部分。
用法：head [选项] [文件]
常用选项：
-n <行数>：显示指定行数，默认为前10行。
tail：显示文件结尾部分。
用法：tail [选项] [文件]
常用选项：
-n <行数>：显示指定行数，默认为后10行。
nano：文本编辑器。
用法：nano [选项] [文件]
按下Ctrl + O保存文件，Ctrl + X退出编辑器。
vi / vim：高级文本编辑器。
用法：vi [文件]
按下I键进入插入模式，编辑文件，按Esc键退出插入模式，输入保存并退出。:wq
文件权限和所有权：

chmod：修改文件或目录的权限。
用法：chmod [选项] 权限模式 文件/目录
常用选项：
u：用户权限。
g：组权限。
o：其他用户权限。
+：添加权限。
-：移除权限。
=：设置权限。
示例： 为文件 添加用户执行权限。chmod u+x script.shscript.sh
chown：修改文件或目录的所有者。
用法：chown [选项] 用户 文件/目录
常用选项：
-R：递归修改文件/目录及其子项的所有者。
示例： 将文件 的所有者修改为 。chown user1 file.txtfile.txtuser1
chgrp：修改文件或目录的所属组。
用法：chgrp [选项] 组 文件/目录
常用选项：
-R：递归修改文件/目录及其子项的所属组。
示例： 将目录 的所属组修改为 。chgrp group1 directorydirectorygroup1
系统信息和管理：

uname：显示系统信息。
用法：uname [选项]
常用选项：
-a：显示全部系统信息。
whoami：显示当前登录的用户名。
用法：whoami
ps：显示进程状态。
用法：ps [选项]
常用选项：
-ef：显示所有进程详细信息。
顶部：实时显示系统资源占用情况。
用法：top
按下Shift + M按内存占用排序，按下Shift + P按CPU占用排序，按Q键退出。
du：显示目录或文件的磁盘使用情况。
用法：du [选项] 目录/文件
常用选项：
-h：以人类可读的格式显示文件大小。
-s：显示总计大小。
df：显示文件系统的磁盘空间使用情况。
用法：df [选项]
常用选项：
-h：以人类可读的格式显示磁盘空间。
shutdown：关机或重启系统。
用法：shutdown [选项] 时间
常用选项：
-r：重启系统。
-h：关闭系统。
网络和连接：

ifconfig：显示和配置网络接口信息。
用法：ifconfig [选项] [网络接口]
示例： 显示网络接口 的详细信息。ifconfig eth0eth0
ping：测试网络连接。
用法：ping [选项] 主机/IP
示例： 测试与 的网络连接。ping www.example.comwww.example.com
ssh：通过SSH连接到远程主机。
用法：ssh [选项] 用户@主机
示例： 通过SSH连接到 主机。ssh user@example.comexample.com
scp：在本地主机和远程主机之间复制文件。
用法：scp [选项] 源文件 目标文件
示例： 将文件 复制到远程主机的用户主目录下。scp file.txt user@example.com:~/file.txt
压缩和解压缩
压缩和解压缩：

tar：打包和解包文件。
用法：tar [选项] 文件/目录
常用选项：
-c：创建压缩文件。
-x：解压缩文件。
-z：使用gzip压缩/解压缩。
-f：指定压缩/解压缩文件名。
gzip：压缩文件。
用法：gzip [选项] 文件
常用选项：
-d：解压缩文件。
-k：保留原始文件。
gunzip：解压缩文件。
用法：gunzip [选项] 文件
zip：创建压缩文件。
用法：zip [选项] 压缩文件名 源文件/目录
常用选项：
-r：递归压缩目录及其内容。
解压缩：解压缩文件。
用法：unzip [选项] 压缩文件
常用选项：
-d：指定解压目录。
管道和重定向
管道和重定向：

|
（管道）：将一个命令的输出作为另一个命令的输入。

示例： 将 命令的输出传递给 命令进行过滤。ls -l | grep ".txt"ls -lgrep
>
（重定向）：将命令的输出重定向到文件。

示例： 将 命令的输出保存到 文件中。ls > file.txtlsfile.txt
>>
（追加重定向）：将命令的输出追加到文件末尾。

示例： 将 “Hello” 追加到 文件的末尾。echo "Hello" >> file.txtfile.txt
<
（输入重定向）：将文件内容作为命令的输入。

示例： 将 文件的内容作为 命令的输入进行排序。sort < file.txtfile.txtsort
任务调度（crond）
概念：

任务调度：按照一定的策略和规则安排和执行任务的过程。
定期任务：在指定的时间间隔或特定时间点执行的任务。
一次性任务：只执行一次的任务。
初始化系统：负责启动和管理操作系统的第一个进程。
方法：

crontab：
编辑 crontab 文件：使用 命令编辑当前用户的 crontab 文件。可以选择编辑现有的任务或创建新的任务。crontab -e
指定任务的执行时间表：在 crontab 文件中，每行代表一个任务，包含了任务的执行时间和要执行的命令。可以使用特定的时间表格式来指定任务的执行时间，例如：。* * * * * command
保存并退出：在编辑完 crontab 文件后，保存并退出编辑器即可。crontab 文件将自动更新。
查看 crontab 内容：使用 命令查看当前用户的 crontab 内容。crontab -l
删除 crontab：使用 命令删除当前用户的 crontab。crontab -r
at：
创建 at 任务：使用 命令创建一个新的 at 任务。然后在交互模式下，输入要执行的命令。时间可以是绝对时间（如 ）或相对时间（如 ）。at 时间12:00now + 1 hour
查看 at 任务队列：使用 命令查看当前用户的 at 任务队列。它将显示待执行的任务及其编号。atq
删除 at 任务：使用 命令删除指定的 at 任务。任务编号可以在 atq 命令的输出中找到。atrm 任务编号
systemd：
创建定时器：创建一个 文件，并定义任务的执行时间间隔或特定的执行时间。定时器文件通常位于 目录或 目录下。.timer/etc/systemd/system//usr/lib/systemd/system/
配置任务执行：在 文件中，指定任务的执行命令和执行方式。可以使用 配置任务的执行命令。.timerExecStart
启用和管理定时器：使用 命令来启用、禁用和管理定时器。例如，使用 启用定时器，使用 启动定时器。systemctlsystemctl enable 定时器名称systemctl start 定时器名称
占位符说明
crontab 占位符说明：
*（星号）：匹配任意值。在时间字段中使用 表示匹配该字段的所有可能值。*
*/n：表示间隔。在时间字段中使用 表示以固定间隔执行，例如 表示每隔 5 个单位执行一次。*/n*/5
n：具体数值。在时间字段中使用具体的数值表示任务在该数值上执行，例如 表示任务在第 5 个单位执行。5
,：列举多个值。在时间字段中使用逗号分隔，表示列举多个值，例如 表示任务在第 1、3、5 个单位执行。1,3,5
-：范围值。在时间字段中使用连字符表示范围，例如 表示任务在第 1 到 5 个单位之间执行。1-5
systemd 定时器占位符说明：
*（星号）：匹配任意值。在时间字段中使用 表示匹配该字段的所有可能值。*
n：具体数值。在时间字段中使用具体的数值表示任务在该数值上执行，例如 表示任务在第 5 个单位执行。5
n-n：范围值。在时间字段中使用连字符表示范围，例如 表示任务在第 1 到 5 个单位之间执行。1-5
*/n：表示间隔。在时间字段中使用 表示以固定间隔执行，例如 表示每隔 5 个单位执行一次。*/n*/5
注意事项：
注意权限：确保任务调度工具有足够的权限执行任务，避免权限不足导致任务执行失败。
日志记录：记录任务的执行日志，以便排查问题和监控任务执行情况。
冲突避免：避免多个任务在同一时间执行，特别是对于涉及共享资源的任务。
安全性考虑：对于包含敏感信息的任务，确保适当的安全措施，如加密、权限控制等。
防火墙
关闭防火墙服务   systemctl stop firewalld.service
禁止防火墙自启动   systemctl disable firewalld.service
管道符|
通才在命令结束后，使用管道设置其他命令 
ls -l /usr/bin |more   分页查看usr/bin目录下的文件
ls -l /usr/bin |grep -n '*test' 过滤 /usr/bin目录下的含有test的文件
grep  |
1.文本过滤       查询文件命令（cat) | grep 内容
2.安装包过滤    安装指令  rpm -qa | grep 内容   ——检索已安装程序
压缩指令
gzip、gunzip 压缩完成后不保留源文件
zip、unzip  压缩完成后保留源文件 （推荐）
tar 集合打包      压缩时为 -zcvf   解压时为 -zxvf
-c 产生.tar打包文件
-v 显示详细信息
-f 指定压缩后的文件名
-z 打包并压缩
-x 解压缩的.tar文件
RPM基础使用
rpm -qa | grep 软件   查看具体包

rpm -qi 软件    查看软件具体信息

rpm -qf  文件路径  逆向查找

rpm -ql 软件（配合grpe使用）  查询文件位置
卸载
rpm -e 卸载
rpm -e 软件 --nodeps 强制删除
安装质量
rpm -ivh  安装包全程称
-install 安装
-verbose 提示
-hash 进度条
挂载
安装火狐
1.将CentOS7挂在在media下 mount /dev/cdrom /media
2.在 /media下查找到CentOS7的挂在文件  
3.检索火狐安装包
4.将安装包复制到 /opt路径中
5.安装火狐  rpm -ivh1.CentOS7挂在media下 mount /dev/cdrom
从YUM端下载MYSQL
1.关闭防火墙
systemctl stop firewalld.service   一次关闭
systemctl disable firewalld.service  禁止开机启动

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
在[mysqld]下添加 skip-grant-tables

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
硬盘
挂载硬盘
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
shell脚本
sh：shell脚本执行器  使用方法：sh 脚本地址（/home/shell/myshell.sh）
chmod u+x myshell.sh：赋予脚本权限可执行脚本
chmod u-x myshell.sh：删除权限无法直接执行脚本
当没有权限时可以使用sh脚本执行器使用
