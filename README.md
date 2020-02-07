# TestNetwork
出国上网测试代码


#### 同时安装wordpress和v2ray
---
文章出处网址：[]()<https://www.atrandys.com/2019/2103.html>

+ 1、使用cent OS 7系统

+ 2、使用以下命令，安装wordpress+v2ray_ws_tls1.3，因为nginx是编译安装，脚本会稍慢一些。  
wordpress+v2ray_ws_tls1.3一键脚本：  
`yum install -y wget vim && wget https://raw.githubusercontent.com/Mars-Ho/TestNetwork/master/v2ray_ws_tls_with_wp.sh && chmod +x v2ray_ws_tls_with_wp.sh && ./v2ray_ws_tls_with_wp.sh`


+ 3、安装完成后，访问域名，开始进入wordpress初始配置页面，自行配置即可。

+ 4、安装完成后，会显示v2ray配置参数，手动填写到v2ray客户端中即可。  
若忘记了，使用以下命令查看参  
`cat /etc/v2ray/myconfig.json`
	+ 修改参数：  
  `vi /etc/v2ray/config.json`  
  `vi /etc/v2ray/myconfig.json`

+ 5、建议搭配BBR使用，速度更快，分享一下网上的BBR一键脚本，先安装内核，重启后再次执行脚本安装加速。  
  + `cd /usr/src && wget -N --no-check-certificate "https://raw.githubusercontent.com/Mars-Ho/TestNetwork/master/tcpPlus.sh" && chmod +x tcpPlus.sh && ./tcpPlus.sh`  
  
  + `cd /usr/src && wget -N --no-check-certificate "https://raw.githubusercontent.com/Mars-Ho/TestNetwork/master/tcp.sh" && chmod +x tcp.sh && ./tcp.sh`

+ 6、再次执行tcp.sh代码，开启网络优化  
  + `cd /usr/src && ./tcpPlus.sh`  

  + `cd /usr/src && ./tcp.sh`

  
  
#### 安装Trojan && BBR
---
注意：安装的前提是必须要有域名。
+ 1、安装一键脚本  
`curl -O https://raw.githubusercontent.com/Mars-Ho/TestNetwork/master/trojan_mult.sh && chmod +x trojan_mult.sh && ./trojan_mult.sh`

  + 修改Trojan的密码  
  `vi /usr/src/trojan/server.conf`
  + 修改完重启同步一下信息  
  `systemctl restart trojan`

+ 2、安装BBR  
  + `cd /usr/src && wget -N --no-check-certificate "https://raw.githubusercontent.com/Mars-Ho/TestNetwork/master/tcpPlus.sh" && chmod +x tcpPlus.sh && ./tcpPlus.sh`  

  + `cd /usr/src && wget -N --no-check-certificate "https://raw.githubusercontent.com/Mars-Ho/TestNetwork/master/tcp.sh" && chmod +x tcp.sh && ./tcp.sh`

Windows下使用FTP客户端，可以在主机中找到网站源文件，路径是/usr/share/nginx/html/目录下
