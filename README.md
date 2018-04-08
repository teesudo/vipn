# vipn
vip private network

this setup is for google cloud with shadowsocks
https://github.com/allenking1028/ss/issues/1

1：sudo -i

(最前面显示root@xxxx)

BBR加速 有两套代码，选其一。

2（第一套）：wget -N --no-check-certificate https://raw.githubusercontent.com/FunctionClub/YankeeBBR/master/bbr.sh && bash bbr.sh install

蓝底窗口按TAB键选NO

选择重启 Y

这里会断开连接，大家可以关掉窗口再重新打开或几秒钟后在界面随便按几个字母 便会提示重新连接。

如果用第一套 就按照顺序继续 第2步完了 第3步 第4步。。。
（第二套） TCP-BBR加速方案 用这套代码 完事以后可以直接到第5步！

wget --no-check-certificate https://github.com/iyuco/scripts/raw/master/bbr.sh
chmod +x bbr.sh
./bbr.sh
复制过去以后便会自动开始当显示./bbr.sh 的时候回车

https://user-images.githubusercontent.com/34980980/38017949-234a1e70-32a6-11e8-823f-9242466d87b7.png

到这个界面的时候再按回车

https://user-images.githubusercontent.com/34980980/37384163-3aeb94ec-2788-11e8-8898-458788f429b8.png

出现这个地方的时候输入y重启 (重启几秒钟后在界面随便按几个字母 便会提示重新连接）然后输入
sudo -i
(最前面显示root@xxxx)
并直接跳转第5步继续
3：sudo -i

(最前面显示root@xxxx)

4：bash bbr.sh start

如果用的第二套代码这3.4 这两步步跳过

5：wget --no-check-certificate https://raw.githubusercontent.com/teddysun/shadowsocks_install/master/shadowsocksR.sh && chmod +x shadowsocksR.sh

6：./shadowsocksR.sh

输入shadowsocks 密码

输入端口号

其他一路回车（也可自行选择混淆 协议）

谷歌云防火墙规则添加 （位置在谷歌云 VPC网络-防火墙）
点击添加新规则，然后按照一下这个设置好。这样 SSR 设置任何端口都可以使用。并且后续不需要再来防火墙规则做设置了。缺点是 所有端口开放。当然也会有一些危险。

https://user-images.githubusercontent.com/34980980/38017949-234a1e70-32a6-11e8-823f-9242466d87b7.png
