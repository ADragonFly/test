# Linux安装Nginx：

1.安装四个依赖包： 
yum -y install gcc zlib zlib-devel pcre-devel openssl openssl-devel

2.创建文件夹、下载文件：
//创建一个文件夹
cd /usr/local
mkdir nginx
cd nginx
//下载、解压tar包
wget http://nginx.org/download/nginx-1.11.7.tar.gz
tar -xvf nginx-1.11.7.tar.gz

3.解压文件：
//进入nginx目录
cd /nginx-1.1.7
//执行命令
./configure
//执行make命令
make
//执行make install命令
make install

4.配置nginx.conf：
//进入目录
cd /conf
//编辑
vi nginx.conf
根据需求改Nginx端口号。
localhost修改为服务器ip地址

5：启动nginx：
进入/usr/local/nginx/sbin目录，输入./nginx即可启动nginx
1. 启动 ./nginx
2. 关闭 ./nginx -s quit  或者 ./nginx -s stop
3. 重启nginx ./nginx -s reload
4. 查看nginx进程  ps aux|grep nginx
5.设置nginx开机启动，只需在rc.local增加启动代码即可。
vim /etc/rc.local
然后在底部增加/usr/local/nginx/sbin/nginx

6.若想使用外部主机连接上虚拟机访问端口，需要关闭虚拟机的防火墙：
centOS6及以前版本使用命令： systemctl stop iptables.service
centOS7关闭防火墙命令： systemctl stop firewalld.service

———————————————————————————————————————————————————————
