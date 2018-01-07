# ShadowsocksR-from-doubi
ShadowsocksR MudbJSON模式多用户一键脚本 支持流量限制等
转自逗比根据地 ， 留作备份

其实这个脚本在当初 ShadowsocksR 单服务器多用户 mudbjson模式使用教程 支持流量限制 文章发布后，我就打算出的，然后因为各种原因拖到现在，然后在上个月底本来因为暂停更新文章一个多月打算写这个来个大的，结果破娃突然不维护ShadowsocksR项目了，我就不知道还要不要写了，于是又搁置了。
直到这段时间内各种人同IP多个马甲在我网站内评论各种说 SSR药丸、SSR辣鸡、大家都去用XX吧等言论，搞得我很烦，这是不是太明显了点？所以我用行动证明，我依然使用并支持ShadowsocksR！
更多的Shadowsocks安装教程/一键脚本请看这里：Shadowsocks指导篇
ShadowsocksR MudbJSON模式 手动安装教程：ShadowsocksR 单服务器多用户 mudbjson模式使用教程 支持流量限制
本脚本的 二维码图片链接，是调用我自建的 二维码API 来生成二维码图片( http://doub.pw/qr/qr.php?text=xxx )。
当访问API页面后，PHP网页文件会把 GET参数( ?text=xxx ) 传递给JS脚本，浏览器会加载JS脚本，然后由JS脚本根据 GET参数的文本 生成二维码图片！图片是在你本地浏览器中生成，服务器中不存在图片！
请确定你信任我和我的脚本，否则请不要用我的脚本，少BB！
系统要求

CentOS 6+ / Debian 6+ / Ubuntu 14.04 +
推荐 Debian 7 x64，这个是我一直使用的系统，我的脚本在这个系统上面出错率最低。并且最容易安装锐速（锐速不支持OpenVZ）
CentOS 7 自带防火墙问题(firewalld)自行解决，其他版本没有做测试。
脚本版本

Ver: 1.0.17
本脚本与另一个SSR脚本 『原创』CentOS/Debian/Ubuntu ShadowsocksR 单/多端口 一键管理脚本 的区别是什么？
ssrmu.sh 脚本是单服务器多用户脚本，使用的是 SSR服务端的MudbJSON模式，可以给每个用户(端口)设置不同的加密方式/协议/混淆/限制速度/设备数限制/可用总流量等功能。即实现单服务器多用户流量管理等功能。
而 ssr.sh 则是单服务器单用户脚本，使用的是 SSR服务端的单用户配置方式，即使实现了多端口，但是还算不算多用户，不支持每个用户(端口)不同的加密方式/协议/混淆等，并且无法管理流量使用。
如何选择这两个脚本？
根据你的需求选择，比如你仅仅是 一个或两个人使用，并且不需要流量管理功能，那么选择 ssr.sh 好了。而如果很多人使用，并且都需要限制流量来管理，那你适合使用 ssrmu.sh ，所以自己看着选，多试试（两个脚本不能共存）！
脚本特点：

所有步骤都可以通过 Shell 脚本中文交互 操作。
支持 限制 用户速度
支持 限制 用户设备数
支持 限制 用户总流量
支持 定时 流量清零
支持 显示 当前连接IP
支持 显示 SS/SSR连接+二维码
支持 一键安装 BBR
支持 一键安装 锐速
支持 一键安装 LotServer
支持 一键封禁 垃圾邮件(SMAP)/BT/PT
安装步骤

简单的来说，如果你什么都不懂，那么你直接一路回车就可以了！
本脚本需要Linux root账户权限才能正常安装运行，所以如果不是 root账号，请先切换为root，如果是 root账号，那么请跳过！
sudo su
输入上面代码回车后会提示你输入当前用户的密码，输入并回车后，没有报错就继续下面的步骤安装ShadowsocksR。
注意：如果你安装的有我的另一个 ssr.sh 脚本，请先卸载ShadowsocksR服务端，再安装这个脚本（不能共存）！
```
wget -N --no-check-certificate https://softs.fun/Bash/ssrmu.sh && chmod +x ssrmu.sh && bash ssrmu.sh
```

备用下载地址（上面的链接无法下载，就用这个）：

```
wget -N --no-check-certificate https://raw.githubusercontent.com/ToyoDAdoubi/doubi/master/ssrmu.sh && chmod +x ssrmu.sh && bash ssrmu.sh

```
本github链接
```
wget -N --no-check-certificate https://raw.githubusercontent.com/yimouleng/ShadowsocksR-from-doubi/master/ssrmu.sh && chmod +x ssrmu.sh && bash ssrmu.sh

```

下载运行后会提示你输入数字来选择要做什么。
输入 1 ，就会开始安装ShadowsocksR服务端，并且会提示你输入Shadowsocks的 端口/密码/加密方式/ 协议/混淆（混淆和协议是通过输入数字选择的） 等参数来添加第一个用户。
注意：用户名不支持中文，如果输入中文会一直保存下去！
如果安装过程中报错，请看 常见问题解决方法。
点击展开 查看更多
请输入要设置的用户 用户名(请勿重复, 用于区分, 不支持中文, 会报错 !)
(默认: doubi):doubi
 
——————————————————————————————
用户名 : doubi
——————————————————————————————
 
请输入要设置的用户 端口(请勿重复, 用于区分)
(默认: 2333):2333
 
——————————————————————————————
端口 : 2333
——————————————————————————————
 
请输入要设置的用户 密码
(默认: doub.io):doub.io
 
——————————————————————————————
密码 : doub.io
——————————————————————————————
 
请选择要设置的用户 加密方式
1. none
[注意] 如果使用 auth_chain_* 系列协议，建议加密方式选择 none (该系列协议自带 RC4 加密)，混淆随意
2. rc4
3. rc4-md5
4. rc4-md5-6
5. aes-128-ctr
6. aes-192-ctr
7. aes-256-ctr
8. aes-128-cfb
9. aes-192-cfb
10. aes-256-cfb
11. aes-128-cfb8
12. aes-192-cfb8
13. aes-256-cfb8
14. salsa20
15. chacha20
16. chacha20-ietf
[注意] salsa20/chacha20-*系列加密方式，需要额外安装依赖 libsodium ，否则会无法启动ShadowsocksR !
 
(默认: 5. aes-128-ctr):5
 
——————————————————————————————
加密 : aes-128-ctr
——————————————————————————————
 
请选择要设置的用户 协议插件
1. origin
2. auth_sha1_v4
3. auth_aes128_md5
4. auth_aes128_sha1
5. auth_chain_a
6. auth_chain_b
[注意] 如果使用 auth_chain_* 系列协议，建议加密方式选择 none (该系列协议自带 RC4 加密)，混淆随意
 
(默认: 2. auth_sha1_v4):2
 
——————————————————————————————
协议 : auth_sha1_v4
——————————————————————————————
 
是否设置 协议插件兼容原版(_compatible)？[Y/n]y
 
请选择要设置的用户 混淆插件
1. plain
2. http_simple
3. http_post
4. random_head
5. tls1.2_ticket_auth
[注意] 如果使用 ShadowsocksR 代理游戏，建议选择 混淆兼容原版或 plain 混淆，然后客户端选择 plain，否则会增加延迟 !
另外, 如果你选择了 tls1.2_ticket_auth，那么客户端可以选择 tls1.2_ticket_fastauth，这样即能伪装特征 又不会增加延迟 !
 
(默认: 5. tls1.2_ticket_auth):5
 
——————————————————————————————
混淆 : tls1.2_ticket_auth
——————————————————————————————
 
是否设置 混淆插件兼容原版(_compatible)？[Y/n]y
 
请输入要设置的用户 欲限制的设备数 ( auth_* 系列协议 不兼容原版才有效 )
[注意] 设备数限制：每个端口同一时间能链接的客户端数量(多端口模式，每个端口都是独立计算)，建议最少 2个。
(默认: 无限):5
 
请输入要设置的用户 单线程 限速上限(单位：KB/S)
[注意] 单线程限速：每个端口 单线程的限速上限，多线程即无效。
(默认: 无限):666
 
请输入要设置的用户 总速度 限速上限(单位：KB/S)
[注意] 端口总限速：每个端口 总速度 限速上限，单个端口整体限速。
(默认: 无限):2333
 
请输入要设置的用户 可使用的总流量上限(单位: GB, 1-838868 GB)
(默认: 无限):1
 
请输入要设置的用户 禁止访问的端口
[注意] 禁止的端口：例如不允许访问 25端口，用户就无法通过SSR代理访问 邮件端口25了，如果禁止了 80,443 那么用户将无法正常访问 http/https 网站。
(默认为空，无限制):
 
——————————————————————————————
禁止的端口 : 无限制
——————————————————————————————
同时最后也会提示是否设置 混淆 兼容原版（也就是使用原版SS也能链接），不懂 直接回车 或 输入 y 。（协议不在兼容原版）
注意：关于限制设备数数，这个协议必须是非原版并且不兼容原版才有效，也就是必须SSR客户端使用协议的情况下，才有效！
不输入一路回车就是 默认参数：
用户 : doubi
端口 : 2333
密码 : doub.io
加密 : aes-128-ctr
协议 : auth_sha1_v4_compatible
混淆 : tls1.2_ticket_auth_compatible
设备数限制: 0(无限)
单线程限速: 0 KB/S (不限速)
端口总限速: 0 KB/S (不限速)
禁止的端口 : 无限制
用户总流量 : 819.21 TB
如果安装过程没有出错，那么最后就会提示：
############################################################
用户 [doubi] 的配置信息：
 
I P : xxx.xxx.xxx.xxx
端口 : 2333
密码 : doub.io
加密 : aes-128-ctr
协议 : auth_sha1_v4_compatible
混淆 : tls1.2_ticket_auth_compatible
设备数限制: 5
单线程限速: 666 KB/S
端口总限速: 2333 KB/S
禁止的端口 : 无限制
 
已使用流量 : 上传: XXX KB + 下载: XXX MB = XXX MB
剩余的流量 : 980 MB
用户总流量 : 1 GB
 
SS链接: ss://xxxxxxxxxxxxx
SS二维码: http://pan.baidu.com/share/qrcode?w=300&h=300&url=ss://xxxxxxxxxxxxx
SSR链接: ssr://xxxxxxxxxxxxx
SSR二维码: http://pan.baidu.com/share/qrcode?w=300&h=300&url=ssr://xxxxxxxxxxxxx
 
提示:
在浏览器中，打开二维码链接，就可以看到二维码图片。
协议和混淆后面的[ _compatible ]，指的是 兼容原版协议/混淆。
 
############################################################
SS/SSR链接（格式： ss://XXXXXXX ，很长），可以从剪辑版导入Shadowsocks客户端，不懂的话看下面二维码。
SS/SSR二维码，复制后面的链接在浏览器打开，就会显示一个二维码的图片，可以用Shadowsocks客户端扫描二维码来添加。
使用说明

运行脚本，
bash ssrmu.sh
 
# 还有一个 运行参数，是用于所有用户流量清零的
bash ssrmu.sh clearall
# 不过不需要管这个，可以通过脚本自动化的设置 crontab 定时运行脚本
输入对应的数字来执行相应的命令。
ShadowsocksR MuJSON一键管理脚本 [vX.X.X]
---- Toyo | doub.io/ss-jc60 ----
 
1. 安装 ShadowsocksR
2. 更新 ShadowsocksR
3. 卸载 ShadowsocksR
4. 安装 libsodium(chacha20)
————————————
5. 查看 账号信息
6. 显示 连接信息
7. 设置 用户配置
8. 手动 修改配置
9. 清零 已用流量
————————————
10. 启动 ShadowsocksR
11. 停止 ShadowsocksR
12. 重启 ShadowsocksR
13. 查看 ShadowsocksR 日志
————————————
14. 其他功能
15. 升级脚本
当前状态: 已安装 并 已启动
 
请输入数字 [1-15]：
注意：添加/删除/修改 用户配置后，无需重启ShadowsocksR服务端，ShadowsocksR服务端会定时读取数据库文件内的信息，不过修改 用户配置后，可能要等个十几秒才能应用最新的配置（因为ShadowsocksR不是实时读取数据库的，所以有间隔时间）。
文件位置

安装目录：/usr/local/shadowsocksr
配置文件：/usr/local/shadowsocksr/user-config.json
数据文件：/usr/local/shadowsocksr/mudb.json
注意：ShadowsocksR服务端不会实时的把流量数据写入 数据库文件，所以脚本读取流量信息也不是实时的！
其他说明

ShadowsocksR 安装后，自动设置为 系统服务，所以支持使用服务来启动/停止等操作，同时支持开机启动。
启动 ShadowsocksR：/etc/init.d/ssrmu start
停止 ShadowsocksR：/etc/init.d/ssrmu stop
重启 ShadowsocksR：/etc/init.d/ssrmu restart
查看 ShadowsocksR状态：/etc/init.d/ssrmu status
ShadowsocksR 默认支持UDP转发，服务端无需任何设置。
本脚本已经集成了 安装/卸载 锐速(ServerSpeeder)/Lotserver，但是是否支持请查看 Linux支持内核列表 。（锐速、LotServer不支持OpenVZ）
 
注意：本脚本中的 显示链接信息中的 获取IP归属地功能使用的是 IPIP.NET 的免费API接口，因为限速所以每秒只能检测一次，同时 IPIP.NET 的免费API接口并不会保证稳定性，可能什么时候就突然暂时失效了，这是本人不可控的，有条件可以自建API接口。
ShadowsocksR目前支持的协议和混淆：

协议（Protocol）：origin，auth_sha1_v4，auth_aes128_md5，auth_aes128_sha1，auth_chain_a，auth_chain_b
混淆（Obfs）：plain，http_simple，http_post，random_head，tls1.2_ticket_auth，tls1.2_ticket_fastauth(这个是客户端用的，而服务端需要选择tls1.2_ticket_auth)
origin 和 plain 是原版，加粗的是推荐使用的。
如果你想要使用 tls1.2_ticket_fastauth 混淆插件，那么服务端选择 tls1.2_ticket_auth，客户端选择 tls1.2_ticket_fastauth 即可。
如果服务端 设置混淆参数为：tls1.2_ticket_auth_compatible (兼容原版)
那么客户端 可使用的混淆为：plain / tls1.2_ticket_auth / tls1.2_ticket_fastauth
tls1.2_ticket_auth 与 tls1.2_ticket_fastauth 的区别为，后者不会等待服务器回应，所以不会增加延迟。适合于，因为混淆插件增加延迟的原因不得不选择原版混淆 plain，但是又因为QOS等因素而处于延迟与干扰/限速等之间抉择的时候，可以选择 tls1.2_ticket_fastauth 客户端混淆插件！
使用阿里云/腾讯云等存着安全组或规则组一类外部防火墙的请注意

点击展开 查看更多
因为阿里云/腾讯云的服务器还有一个外部的防火墙也就是叫 安全组或规则组。
一般来说默认是只开放 22(SSH)端口，所以一些人在搭建ShadowsocksR服务端后，会出现无法访问的情况，ShadowsocksR客户端的统计窗口显示超时。
同时ShadowsocksR服务端开启详细日志模式(其他功能中)后，ShadowsocksR客户端访问ShadowsocksR账号无日志输出。
ShadowsocksR 端口限速中 单线程限速 和 端口总限速 的区别

注意：如果要使用脚本中的这个功能，需要重新下载脚本，并重装安装 2月15日 以后的ShadowsocksR服务端才行。
请查看这个文章：ShadowsocksR服务端 限制设备连接数 和 限制端口速度 的方法
解决 可使用原版协议，但无法使用ShadowsocksR协议 的问题

点击展开 查看更多
如果发现Shadowsocks原版协议/混淆可以使用，而ShadowsocksR的协议/混淆无法使用，那么多半是 VPS时区问题
这个命令，我的ShadowsocksR脚本在安装的时候已经执行了，如果你发现没有执行，那你可以手动执行。
我们可以通过下面这个命令，把VPS的时区调整为北京时区，这样就避免了ShadowsocksR 协议/混淆 因为时差太大造成的无法验证。
cp /usr/share/zoneinfo/Asia/Shanghai /etc/localtime
注意，部分VPS会提示你是否覆盖文件，输入 y 然后回车。
如果你遇到，crontab设定的定时任务不按更换时区后的VPS时间执行，那么请看下面：
crontab设定的定时任务不按VPS的时间执行，那是因为你更换VPS时区后还需要重启crontab。
CentOS 系统：
/etc/init.d/crond restart
Debian/Ubuntu 系统：
/etc/init.d/cron restart
提示 Media change: please insert the disc labeled‘Debian GNU/Linux 7.0.0 Wheezy — Official amd64 CD 等信息是 apt源 的问题，更换 apt源

点击展开 查看解决办法
我发现有一些人的VPS的 apt源有问题，导致安装失败，所以我这里写上如何更换 apt源。
本步骤仅适合 Debian 系统，Ubuntu系统自行搜索 apt源。
下面的手动改的方法一些人可能嫌麻烦，所以你们可以这样字更换apt源。
依次输入就可以更换apt源了，下面的代码是以 us美国 为例，你可以自己去这里选一个近一些合适的，然后替换下面代码中 us.sources.list 的 us 。
wget -N --no-check-certificate -P /etc/apt https://softs.fun/Bash/sources/us.sources.list
rm -rf /etc/apt/sources.list
cp /etc/apt/us.sources.list /etc/apt/sources.list
手动更换（上面的命令执行完毕就不要重复执行这个了）
打开你的apt源文件，
vi /etc/apt/sources.list
然后按 I 键 进入编辑模式，如果你没有安装vim，也无法通过 apt-get install vim -y 安装，那么你就只能通过SFTP下载这个文件本地编辑了。
把下面的内容复制过去，注意下面示例是美国的apt源，想要其他地区的apt源，请看：Debian全球镜像站（替换下面的 ftp.us.debian.org 中的 us ）
deb http://ftp.us.debian.org/debian/ jessie main
deb-src http://ftp.us.debian.org/debian/ jessie main
 
deb http://security.debian.org/ jessie/updates main contrib
deb-src http://security.debian.org/ jessie/updates main contrib
 
# jessie-updates, previously known as 'volatile'
deb http://ftp.us.debian.org/debian/ jessie-updates main contrib
deb-src http://ftp.us.debian.org/debian/ jessie-updates main contrib
修改完毕之后，按 ESC 键 退出编辑模式，然后输入 :wq 保存并退出，然后再试一试 apt-get update 是否正常。
ShadowsocksR启动失败，日志提示：Exception: libsodium not found 的错误

这是你使用了 chacha20 系列加密方式，但是却没有安装 libsodium支持库，导致ShadowsocksR无法启动，运行脚本选择选项 4 安装 libsodium支持库即可，如果安装失败，请选择其他的加密方式，对速度影响不大。
提示wget: unknown host “softs.fun” 之类的错误

这是无法解析我的域名，多半是DNS的问题，请更换DNS为谷歌DNS。
点击展开 查看更多
echo "nameserver 8.8.8.8
nameserver 8.8.4.4" > /etc/resolv.conf
# 两行一起复制一直执行
提示 wget: command not found 的错误

这是你的系统精简的太干净了，wget都没有安装，所以需要安装wget。
点击展开 查看更多
CentOS系统:
yum install -y wget
Debian/Ubuntu系统:
apt-get install -y wget
升级脚本

升级脚本只需要重新下载脚本文件就可以了，会自动覆盖原文件。
定时重启

一些人可能需要定时重启ShadowsocksR服务端来保证稳定性等，所以这里用 crontab 定时。
点击展开 查看更多
crontab -e
# 首先打开定时设置，然后会出现文本编辑，按 I键 进入编辑模式，根据需求添加下下面的代码到 这个文本编辑框内！！
------------
# 如果提示命令不存在，那么安装crontab：
# CentOS系统：
yum update
yum install -y crond
# Debian/Ubuntu系统：
apt-get update
apt-get install -y cron
安装并打开 crontab 后，我们根据需求添加下面的代码，添加后我们按 ESC键 退出编辑模式，然后输入 :wq 保存并退出。
# 添加定时重启任务
# 是添加到 crontab -e 文本编辑框内，而不是让你执行！
# 下面代码前面的 * * * * * 分别对应：分钟 小时 日 月 星期
 
10 2 * * * /etc/init.d/ssr restart
# 这个代表 每天2点10分重启一次 ShadowsocksR
 
10 2 */2 * * /etc/init.d/ssr restart
# 这个代表 每隔2天的2点10分重启一次 ShadowsocksR
 
10 */4 * * * /etc/init.d/ssr restart
# 这个代表 每隔4小时的第10分重启一次 ShadowsocksR
更新日志

2017年11月03日，版本 v1.0.17
1. 修改 SSR服务端安装方式为：ZIP压缩包安装（考虑到SSR服务端不更新了，所以为了降低git依赖安装出错率，就改成zip压缩包了）。
2. 修改 JQ安装方式为：集成与SSR服务端文件夹内（减少了一个安装JQ的下载步骤，节省时间）。
2017年10月23日，版本 v1.0.16
1.新增 支持自定义用户配置中显示的IP或域名（包括SS/SSR链接）。
—— 考虑到一些人的服务器有多个外网IP，而服务端搭建者只希望用户使用某个IP，那么可以用这个功能指定IP。同样也可以指定为域名（当然你需要有个域名解析为你这个服务器的IP），修改选项为：7. 设置 用户配置 -> 13. 修改 用户配置中显示的IP或域名
2017年10月06日，版本 v1.0.15
1.恢复 libsodium以前安装方式。
2017年10月04日，版本 v1.0.14
1. 修复 当用户名最后一个符号是 “]” 时，添加用户账号配置 提示用户名已存在的问题（前提是添加了一个同名用户名，例如 doubi 然后再去添加 doubi] 就会触发BUG）。
2017年09月22日，版本 v1.0.13
1.修复 因为系统缺少automake，而libsodium安装失败的问题。
点击展开 查看更多
2017年09月22日，版本 v1.0.12
1.更新 libsodium最新版本安装方式。
2017年09月18日，版本 v1.0.11
1. 新增 IPv6防火墙开放端口规则功能（原先只开放IPv4防火墙）。
2017年09月03日，版本 v1.0.10
1. 新增 查看 账号信息 时显示 已使用流量。
2. 优化 查看 账号信息 显示格式。
2017年08月31日，版本 v1.0.9
1.修复 显示链接信息 功能，不同端口 链接IP显示重复的问题(例如链接 8080端口的IP同样显示在 80端口下)
2017年08月24日，版本 v1.0.8

1.新增 几个外网IP获取源，避免一些服务器获取外网IP失败。
2017年08月13日，版本 v1.0.7

1.修复 切换日志模式后，ShadowsocksR启动失败的问题。
2017年08月12日，版本 v1.0.6

1.修复 封禁/解封 BT/PT/SPAM功能运行后没有正常删除脚本的问题。
2017年08月12日，版本 v1.0.5

1.取消 添加/删除/修改 用户配置后，会重启ShadowsocksR服务端的代码。
—— 我也是一直不知道可以动态读取数据文件内的配置，不过我测试发现可能修改后需要等个十几秒才能应用最新配置！
2017年08月11日，版本 v1.0.4

1.取消 安装ShadowsocksR过程中修改DNS为谷歌DNS的步骤（个别服务器会导致未知问题）。
2017年08月10日，版本 v1.0.3

1.修改 设置用户禁止访问的端口默认值为空。
2017年08月10日，版本 v1.0.2

1.修复 BBR文件下载的位置问题。
2.修复 升级脚本功能中，下载 ssrmu.sh 位置错误问题。
2017年08月10日，版本 v1.0.1

1.修复 BBR文件位置问题。
2017年08月09日，版本 v1.0.0

1.推出 正式版本。
