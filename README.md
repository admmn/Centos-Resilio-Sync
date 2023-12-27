文章来自https://codeleading.com/article/34242907784/

Centos7 安装 Resilio Sync
下载
Resilio Sync下载地址，找到自己系统环境的下载链接。

以我的 64 位环境为例：
1. wget https://download-cdn.resilio.com/stable/linux-x64/resilio-sync_x64.tar.gz

解压
1. cd
2. mkdir resilio-sync
3. cd resilio-sync
4.  tar -zxvf resilio-sync_x64.tar.gz

导出配置文件
1. ./rslsync --dump-sample-config > sync.conf

设置开机启动
编辑 rc.local 文件
1. vi /etc/rc.local

添加到文件中
1. cd /root/resilio-sync
2. ./rslsync --config sync.conf

更改文件执行权限
1. chmod -R 755 /etc/rc.d/rc.local

启动
1. ./rslsync --config sync.conf

通过Web登陆
默认地址：https://ip:8888，相关设置可以在配置文件 sync.conf 中修改。

设置好用户名、密码重新登陆添加同步文件夹即可。
