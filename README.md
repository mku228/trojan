# 小白科学上网一键Trojan搭建VPN梯子最新2022教程 

# 第一部分：什么是 Trojan

Trojan将流量伪装成用户正常访问网页时的HTTPS流量，防止流量被检测和干扰。敏敢时期，基本上只有Trojan和V2Ray伪装能提供稳如狗的体验。

本文提供图文教程，整合了网上最简便的方法，对小白比较友好，基本上按着教程一步步走就能搭好。

# 第二部分：搭建前准备

一台VPS服务器：

# 国外服务器vps注册创建教程


很多时候我们需要使用 Google 查询第一手资料，比如官方的文档网站，或者一些文献，虽然市面上有一些 VPN 工具，但是它们不是很稳定，并且不是很安全，比较好的方式就是自己搭建一个属于自己的 VPN 服务，自己掌控。

## 优惠购买云服务器vultr

在搭建之前需要一台境外的云服务器，而 [vultr](https://www.vultr.com/?ref=8944093-8H) 服务商比较稳定，安全，相当于境内的阿里云。

值得说的一点是， [vultr](https://www.vultr.com/?ref=8944093-8H) 给新用户的福利相当给力，充值 10 美元就可以获取 100 美元，你可以点击 [vultr 专属赠送新用户 100 美元](https://www.vultr.com/?ref=8944093-8H) 进去抢先注册。

右上角有注册按钮，你也可以切换成中文界面：

<img width="1446" alt="vpn搭建教程" src="https://user-images.githubusercontent.com/84239400/119019442-be0cc500-b98c-11eb-895b-0d6300dce93d.png">

![](https://user-images.githubusercontent.com/84239400/119019760-0d52f580-b98d-11eb-9837-aba0990f1dfb.png)

接着使用邮箱和密码就可以注册了。

![](https://user-images.githubusercontent.com/84239400/119020042-4ee3a080-b98d-11eb-8341-bfc30f4b103c.png)

进去之后你可以看到这个页面，说明你已经通过 [vultr 专属优惠链接](https://www.vultr.com/?ref=8872890-6G) 获得了 100 美元赠送的资格：

![](https://user-images.githubusercontent.com/84239400/119020173-733f7d00-b98d-11eb-8ecc-a1afeb556fe6.png)

现在你只要选择支付宝充值 10 美元以上，就可以获得额外赠送的 100 美元。

![](https://user-images.githubusercontent.com/84239400/119020280-966a2c80-b98d-11eb-9113-8f5f0b75c5ea.png)

接下来就可以在这个平台选购云服务器了。

点击页面左边菜单栏的 「Products」进入服务器选购页面。

### Choose Server 选择服务器

选择 Cloud Compute 即可：

![](https://user-images.githubusercontent.com/84239400/119020373-af72dd80-b98d-11eb-8478-02d735b82709.png)

### Server Location

服务器的位置，可以选择美国地区，比如纽约：

![](https://user-images.githubusercontent.com/84239400/119020467-cadde880-b98d-11eb-8927-d3d837bbc20c.png)

选择服务器配置，看个人情况。$5适合个人搭梯子。

### Server Type

服务器类型，CentOS 8 x64 系统：

<img width="1297" alt="vpn搭建教程" src="https://user-images.githubusercontent.com/84239400/119020720-198b8280-b98e-11eb-9df3-19bf5a187a1e.png">

### Server Size

内存，个人使用10G完全够用，这里选择3.5美元一个月，性价比高，注意不要选择IPv6 ONLY的，要不然无法搭建使用。

<img width="1240" alt="vpn搭建教程" src="https://user-images.githubusercontent.com/84239400/119020895-4a6bb780-b98e-11eb-9ac8-3cdd4f4397de.png">

选择完了之后，下面的其它东西都不需要填，直接点击右下角 Deploy Now 就可以了：

![](https://user-images.githubusercontent.com/84239400/119020981-68391c80-b98e-11eb-9f16-00c75de88eeb.png)

这时候你就拥有了自己的一台云服务器了：

<img width="1261" alt="VPN搭建教程" src="https://user-images.githubusercontent.com/84239400/119021075-86068180-b98e-11eb-82a9-71edb9934f23.png">


点击 Cloud Instance ，可以看到你服务器的 IP 地址和密码：

<img width="1308" alt="vpn搭建教程" src="https://user-images.githubusercontent.com/84239400/119021183-a20a2300-b98e-11eb-8ff4-7f18d3e3bb80.png">


## 连接到你的服务器

### windows 系统连接到 vultr 服务器

windows 可以下载[PuTTY](https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html)工具。

打开之后选择 session，将你在 vultr 网上得到的服务器 ip 复制过来，输入到这里：

![](https://user-images.githubusercontent.com/84239400/119023900-037fc100-b992-11eb-85ea-525a61a69657.png)

Port 默认 22，Connection Type 选择 SSH，接着点击 Open，连接进去之后输入你云服务器的密码。

### Linux 和 MacOS 连接到 vultr 服务器

Linux 和 MacOS 可以打开终端，使用如下命令连接：

```
ssh root@xx.xx.xxx.xx
```

`xx.xx.xxx.xx`就是你的服务器上的 IP 地址。

连接进去之后输入 yes 后按回车，接着输入你云服务器的密码，即可使用云服务器。

<img width="772" alt="vpn搭建教程" src="https://user-images.githubusercontent.com/84239400/119024049-32963280-b992-11eb-8c05-db6df1f7fbfa.png">

注意！有小概率情况是，如果你选日本机房，可能被自动分配到被墙的IP。如何判别呢？打开 http://ping.chinaz.com 输入你的服务器IP测试。如果Ping不通，说明IP被墙了。立即删掉这台服务器，重新创建一
个。


## 域名申请
目前顶级域名我知道的只有freenom可免费申请，官网： http://www.freenom.com/zh/index.html

如果不知道怎么申请，百度【怎么申请freenom免费域名】

如：我这里申请了一个demo.com的域名，当然你也可以买腾讯云或者阿里云上面的域名。

## DNS 解析
这里我在freenom上申请了免费域名，就以freenom解析为例

1.进入freenom主页：https://my.freenom.com/clientarea.php
2.点击右上角 Services ==> My Domains
3.点击域名后面 Manage Domain按钮
4.点击Manage Freenom DNS管理DNS
4.添加一条记录Name填www、Type填A、TTL默认、Target填你服务器VPS的IP地址，点击保存Save Change
6.好了，这里就完成DNS解析了，如果你是其他域名商的，请自行百度解析。

## 端口开放

安装前必须开放服务器的80和443端口

防火墙相关命令可阅读 ：https://www.itblogcn.com/article/vultr-centos-7-firewall.html


# 一键Trojan搭建

系统建议：

CentOS 7
首先安装wget（Vultr VPS已安装）

```
yum install -y wget
```


## 一键安装Trojan脚本
输入以下命令，回车执行（shift+insert可粘贴）
```
wget -N --no-check-certificate -q -O trojan_install.sh "https://raw.githubusercontent.com/V2RaySSR/Trojan/master/trojan_install.sh" && chmod +x trojan_install.sh && bash trojan_install.shCOPY
```
输入1回车

![image](https://user-images.githubusercontent.com/98797623/152640698-41d452d3-8a5e-486d-af84-09e95bb851db.png)

输入你解析的域名，比如我解析的是www.demo.com，然后回车执行

![image](https://user-images.githubusercontent.com/98797623/152640709-4ebc7a3f-fbcb-4904-99fc-b8cf1e1bc6f7.png)

如果解析不正常，可能是之前DNS解析还没生效，建议等几分钟重试。

显示一下信息代表安装成功：

![image](https://user-images.githubusercontent.com/98797623/152640713-620126f9-1782-4ad5-9932-c76ff7b6fa65.png)

查看配置文件(该配置在后面链接时使用)：

输入以下命令，回车执行（shift+insert可粘贴）

```
cat /usr/src/trojan-macos/trojan/config.json
```

我的配置如下：

```
{
    "run_type": "client",
    "local_addr": "127.0.0.1",
    "local_port": 1080,
    "remote_addr": "www.demo.com",
    "remote_port": 443,
    "password": [
        "ae412345"
    ],
    "log_level": 1,
    "ssl": {
        "verify": true,
        "verify_hostname": true,
        "cert": "",
        "cipher": "ECDHE-ECDSA-AES128-GCM-SHA256:...",
        "cipher_tls13": "TLS_AES_128_GCM_SHA256:...",
        "sni": "",
        "alpn": [
            "h2",
            "http/1.1"
        ],
        "reuse_session": true,
        "session_ticket": false,
        "curves": ""
    },
    "tcp": {
        "no_delay": true,
        "keep_alive": true,
        "reuse_port": false,
        "fast_open": false,
        "fast_open_qlen": 20
    }
}
```

## 请重点关注配置文件中的如下参数：

remote_addr：服务器地址（浏览器输入这个地址能打开网页）
remote_port：端口
password：密码


# 第五部分：客户端链接Trojan
各平台的Trojan客户端地址：

##Windows Trojan客户端：
【v2rayN】：https://cloud.degoo.com/share/f-Vljc2ZjhmcPyHbi5Pw0A

解压后，点击v2rayN.exe启动

进行配置:

注意电脑右下角 V 图标，双击图标，点右上角 服务器 ==> 添加[Trojan]服务器。

客户端的配置需要根据你的服务端进行相应的配置，我的域名是www.demo.com，配置如下图：

![image](https://user-images.githubusercontent.com/98797623/152640734-6ddfc55e-7b97-4cc9-94f5-ff19f3285d49.png)
保存后，右键电脑右下角 V 图标，Http待理==>开启PAC,并自动配置系统待理(PAC模式)

![image](https://user-images.githubusercontent.com/98797623/152640741-b82490ac-db02-4aab-bb32-2f2f7acd3999.png)

## Android Trojan客户端：
下载方式一：网盘(APK直接安装)

【APK】：https://cloud.degoo.com/share/msgcYbsWQVoz2EIbSXr5bw

下载方式二：GitHub
一般手机是arm架构，我就直接给出对应客户端了，其他架构需要你去网上找设备相应的CPU架构并进行选择下载：
【v2rayNG Github Releases】https://github.com/2dust/v2rayNG/releases/download/1.4.13/v2rayNG_1.4.13_arm64-v8a.apk

使用方法:

```
(1）打开 v2rayNG APP
(2）点击右上角 + 号
(3）选择 手动输入[Trojan]
(4）别名随意，地址(`remote_addr`)，端口(`remote_port`)，密码(`password`)，其他设置默认
(5）右上角 √ 保存
(6）右下角 V图标 点击启动.
(7）打开浏览器试试吧
```
MacOS Trojan客户端:
https://github.com/Cenmrev/V2RayX/releases

Linux内核 Trojan客户端：
Debian、Ubantu、CentOS等电脑桌面发行版（不能完全通用，可以尝试一下）
https://github.com/jiangxufeng/v2rayL/releases

IOS Trojan客户端：
需要国外账号，推荐shadow（小火箭）rocket，quantumult（圈），kitsunebi

测试
打开浏览器，访问www.google.com，如下：

![image](https://user-images.githubusercontent.com/98797623/152640761-a0a2fa15-42ef-4d0f-a930-28205f3f9bb5.png)


Trojan搭建教程到此结束，祝大家春风得意！




