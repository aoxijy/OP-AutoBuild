# OP-AutoBuild
使用 GitHub Actions 云编译OpenWrt 每星期编译更新固件
特性
每周更新并发布到Release；
包含Luci绝大多数常用插件；
所有软件包均包含依赖ipk，不用再去为了一个依赖ipk东奔西找。
食用方法
去Release下载文件 ，并确认SHA256是否匹配；x86-64-IPK.tar.gz
确认文件完整后打开压缩包，进入目录 ，里面有几个文件夹，然后将文件夹里面所有的ipk文件解压到桌面（桌面新建文件夹）；openwrt\packages\x86_64\
寻找需要的软件包并复制软件包全名（例如passwall）；
使用WinScp登录OpenWrt，切换到tmp目录下，将需要的软件包拖入此目录；
登录OpenWrt SSH，输入 切换到tmp目录；cd /tmp
输入 ，回车；opkg install 刚刚你复制的软件包名.ipk
若提示缺少依赖，复制软件包名去解压的那个文件夹查找，把依赖软件包装上，具体过程同上，然后再装你需要的软件包；
安装完成登入后台进行使用。
提醒
建议先将OPKG源更换为一个速度相对比较快且稳定的源，再执行 更新源列表，这样可以省掉很多找某些依赖的时间（这里提供一个中国科技大学Linux用户协会OpenWrt镜像源： ）。opkg updatehttps://openwrt.proxy.ustclug.org/
如果是用来更新本地已安装但较旧版本的软件包，建议先备份本地软件包内的数据（例如节点信息），然后执行卸载，将依赖等一并卸载，再按照上面的教程进行安装，避免各种玄学原因装不上。
不建议安装后台主题软件包，可能会导致后台Web页面瘫痪，若非要使用请做好备份。
非X86-64架构请勿使用本软件包！
折腾必有风险，所以建议在安装任何一个软件包折腾前务必做好备份工作，以免出现不必要的麻烦。出现任何后果概不负责。
致谢
本项目是站在巨人的肩膀上完成的，没有他们的贡献不可能有这个项目，在此表示感谢。他们分别是：

P3TERX 可以自行根据他的文章学习然后编译适合自己的OpenWrt。
rabbitwit
Microsoft
Microsoft Azure
GitHub
GitHub Actions
tmate
mxschmitt/action-tmate
csexton/debugger-action
Cisco
OpenWrt
Lean's OpenWrt
Cowtransfer
WeTransfer
Mikubill/transfer
