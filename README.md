Centos7 安装 Resilio Sync
下载
Resilio Sync下载地址，找到自己系统环境的下载链接。
https://www.resilio.com/platforms/desktop/

以我的 64 位环境为例：

wget https://download-cdn.resilio.com/stable/linux-x64/resilio-sync_x64.tar.gz
1
解压
cd
mkdir resilio-sync
cd resilio-sync
tar -zxvf resilio-sync_x64.tar.gz
1
2
3
4
导出配置文件
./rslsync --dump-sample-config > sync.conf
1
设置开机启动
编辑 rc.local 文件

vi /etc/rc.local
1
添加到文件中

cd /root/resilio-sync
./rslsync --config sync.conf
1
2
更改文件执行权限

chmod -R 755 /etc/rc.d/rc.local
1
启动
./rslsync --config sync.conf
1
通过Web登陆
默认地址：https://ip:8888，相关设置可以在配置文件 sync.conf 中修改。

设置好用户名、密码重新登陆添加同步文件夹即可。
