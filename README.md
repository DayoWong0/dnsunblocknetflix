# dnsunblocknetflix


dns解锁流媒体介绍：

解锁服务是一项采用了特殊的技术以解除各种流媒体服务地域限制的付费DNS解析服务。

它有什么用？
正如之前所说，它能用于解锁各种流媒体服务的地域限制

支持在什么设备上使用？
支持任何允许修改DNS的设备，包括但不限于Windows、macOS、Linux(各种发行版)、iOS、Android、各种路由器设备。
在直接使用，不部署在代理服务器的情况下，Android TV 下的 Netflix 客户端会出现速率低下或者无法使用的问题，您可以点击下方的按钮查看相应的解决方案。


路由器配置SS服务器
梅林固件配置SS服务器解决Android Netflix TV 客户端速率低下的问题。
该教程目前仅适用于梅林固件，其它固件请确认能够正常搭建/启用SS(R)服务器，仅支持SS(R)客户端不能使用该方法。

该方法允许配合DDNS服务实现4G网络下解锁流媒体服务。

编写本文时使用的路由器型号：华硕 RT-AC86U

通过浏览器访问路由器管理界面，默认管理地址为：192.168.50.1 或 router.asus.com​

登录后，进入路由器管理界面首页，点击「高级设置」下的「外部网络(WAN)」。

然后在 「 DNS 服务器1」或「DNS 服务器2」（部分型号无 DNS 服务器2）框中输入在产品控制面板上显示的DNS 节点 IP，最后点击下方的「应用本页面设置」来保存修改。（该操作会重新拨号，保存后请检查您的公网IP，如果出现变动请重新前往产品控制面板添加授权）

前往梅林的「 软件中心」，找到「 ss-server」(图中左侧第一个)，如果没安装，可以切换到未安装选项卡安装该插件。
安装完成后，点击绿色小飞机进入插件配置页面。

进入插件配置页面后，依次填写您要设置的SS服务器信息，建议按照图例进行配置。密码请不要设置过于简单。
不要开启 「 使用ss网络」，设置SS服务器不会影响到您的科学上网插件的正常使用。

Android SSR 客户端不支持设置该混淆协议，「混淆」请保持关闭！

「UDP转发」必须开启！否则将无法正常使用。



Windows配置SS服务器
Windows 配置SS服务器解决Android Netflix TV 客户端速率低下的问题。
编写本文时使用的系统版本：Windows 10 (1803)

该软件需要您的系统版本高于 Windows 7。

设置DNS
首先您需要在您的 Windows 设备的「网络连接」处选择您的网络适配器，并将 DNS 修改为 TVCAT DNS 节点的IP，具体操作方法可以点击下方的按钮转到教程页面查看。

Windows 修改 DNS
/windows
或者通过执行产品控制面板上显示的命令来一键修改。命令类似于下方的内容：(此处的命令仅做示例，不能使用)

netsh interface ip set dns "以太网" static 1.1.1.1 && netsh interface ip add dns "以太网"  1.0.0.1
上方的命令需要以管理员身份运行，如果您使用的是Windows10，可以直接在任务栏Windows 徽标右侧的搜索框（按钮）搜索CMD并在匹配结果上右键以管理员身份运行。

下载软件
DNS设置完成后，您需要下载SS服务端软件，您可以点击下方的链接来下载。
SS服务端软件：https://my.tvcat.net/dl.php?type=d&id=1​

配置使用
1.下载完成后，解压并打开 ss-server 文件夹。
2.在使用前请阅读 使用教程.txt 文件。
3.配置 config.json，下方为示例内容，请直接对照修改文件夹内的配置文件，修改完成后保存

{
    "server":"0.0.0.0",
    "server_port":5200, //如无必要，保持默认
    "local_address":"127.0.0.1",
    "local_port":1080, //如无必要，请保持默认
    "password":"pass", // pass 修改为您要设置的密码
    "timeout":600,
    "method":"chacha20",
    "http_proxy": false
}
4.点击 运行.bat 开启SS服务端。运行期间请不要关闭窗口。

SS客户端不支持该解决方案，请使用SSR客户端。

5.现在您可以在您的Android TV上安装SSR客户端并填写上述配置并连接。

其中协议 & 混淆均选择第一个（最上面的一个选项），分别是 origin 和 plain ，然后在将界面划动到最下方，将UDP转发打开。

Android SSR 客户端下载地址： ssr_3.4.0.6.apk
设置连接信息时，服务器地址应填您的电脑局域网IP地址，您可以在路由器内查看或者在电脑上按Win+R 输入CMD 并确定，在弹出的框中输入 ipconfig /all 按回车查看。

在Android TV设备连接SSR后，此时可以尝试是否解锁成功。

如果出现整个系统没有网络的情况，可以尝试将「UDP转发」关闭。

设置完成后，点击顶部的「开启ss-server」，来完成SS服务器的配置。

SS客户端不支持该解决方案，请使用SSR客户端。

现在您可以在您的Android TV上安装SSR客户端并填写上述配置并连接。

其中协议 & 混淆均选择第一个（最上面的一个选项），分别是 origin 和 plain ，然后在将界面划动到最下方，将UDP转发打开。

Android SSR 客户端下载地址： ssr_3.4.0.6.apk
设置连接信息时，服务器地址应填您的路由器IP地址，例如本次教程中服务器地址应为 192.168.50.1

在Android TV设备连接SSR后，此时可以尝试是否解锁成功。

如果出现整个系统没有网络的情况，可以尝试将「UDP转发」关闭。



流媒体支持范围
您可以在下方查看 TVCAT 视讯解锁服务支持的流媒体服务范围。
这是一个持续更新的列表。

最后更新于：2019.4.14

名称

地域

Netflix

香港、台湾、英国、美国、日本

Hulu

美国

HBO GO

美国、英国、香港

Prime Video (Amazon)

香港、台湾、英国、美国、日本

ABC

美国

BBC iPlayer

英国

TVB

香港

动画疯

台湾

LineTV

台湾

BiliBili (哔哩哔哩)

台湾

 Abema TV

日本

linux（centos）修改dns一键脚本 最后的ip需要更改
chattr -i /etc/resolv.conf && wget -N --no-check-certificate https://shop.bgp.sh/modules/addons/stream_unblock/library/shell/dns-change.sh && chmod +x dns-change.sh && ./dns-change.sh 8.8.8.8 
改完后输入 reboot 重启系统

