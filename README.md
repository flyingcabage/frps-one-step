# frps-one-step
frps一键安装脚本


#安装 

```sh
wget --no-check-certificate https://raw.githubusercontent.com/panw3i/frps-one-step/master/install-frps.sh
chmod 700 ./install-frps.sh
./install-frps.sh install
```

#说明
```shell
Loading network version for frps, please wait...
frps Latest release file frp_0.8.1_linux_amd64.tar.gz    #此步骤会自动获取frp最新版本，自动操作，无需理会
Loading You Server IP, please wait...
You Server IP:12.12.12.12                                           #自动获取你服务器的IP地址
Please input your server setting:

Please input frps bind_port [1-65535](Default Server Port: 5443):      #输入frp提供服务的端口，用于服务器端和客户端通信
Please input frps dashboard_port [1-65535](Default dashboard_port: 6443): #输入frp的控制台服务端口，用于查看frp工作状态
Please input frps vhost_http_port [1-65535](Default vhost_http_port: 80):  #输入frp进行http穿透的http服务端口
Please input frps vhost_https_port [1-65535](Default vhost_https_port: 443): #输入frp进行https穿透的https服务端口
Please input privilege_token (Default: WEWLRgwRjIJVPx2kuqzkGnvuftPLQniq): #输入frp服务器和客户端通信的密码，默认是随机生成的
Please input frps max_pool_count [1-200](Default max_pool_count: 50):     #设置每个代理可以创建的连接池上限，默认50

##### Please select log_level #####
1: info
2: warn
3: error
4: debug
#####################################################
Enter your choice (1, 2, 3, 4 or exit. default [1]):        #设置日志等级，4个选项，默认是info


Please input frps log_max_days [1-30]
(Default log_max_days: 3 day):            #设置日志保留天数，范围是1到30天，默认保留3天。

##### Please select log_file #####
1: enable
2: disable
#####################################################
Enter your choice (1, 2 or exit. default [1]):      #设置是否开启日志记录，默认开启，开启后日志等级及保留天数生效，否则等级和保留天数无效

```

#客户端配置
```ini
[common]
server_addr = 39.108.123.145  
server_port = 5443  

[web]
type = http
local_port = 8086
custom_domains = 39.108.123.145
```

#命令
```shell
./install-frps.sh update      更新命令
./install-frps.sh uninstall     卸载命令/etc/init.d/frps start
/etc/init.d/frps stop
/etc/init.d/frps restart
/etc/init.d/frps status
/etc/init.d/frps config
/etc/init.d/frps version
```



