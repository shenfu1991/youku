#优酷路由宝 yk-L1降级获取root，刷breed


1、刷降级固件

因为新版路由宝固件已经无法通过替换stok方法来删除root密码开启telnet，所以这里我们直接刷入已经开启telnet和SSH的降级固件。原帖里有所需要的文件下载地址，但是我使用他的降级固件不知为何没有效果，在这里我提供自己在网上找到的可以使用的降级固件。

在路由宝网页界面点手动升级，选择上面的降级固件。就可以刷进去了。刷完后实际上也已经root了可以使用SSH，用户名：root 密码：admin。

拥有root权限的固件：https://raw.githubusercontent.com/mengzhihoing/youku/master/Youku-L1c-0818-root.bin

2、刷不死Breed

网上大部分教程都是教大家刷不死U-boot，我选择刷同一个作者新开发的Breed，他具有U-boot所有的功能，但更稳定高效。

介绍网址在这里

SSH登上路由宝后（win下推荐使用putty，linux和mac下自带控制台SSH客户端），输入以下命令

cd /tmp  

wget http://breed.hackpascal.net/breed-mt7620-youku-yk1.bin   
或者  
wget https://raw.githubusercontent.com/mengzhihoing/youku/master/breed-mt7620-youku-yk1.bin  
  
mtd -r write /tmp/breed-mt7620-youku-yk1.bin mtd1  
成功之后路由器会自动重启，重新连接后，按住路由器复位键不松手，断电，插电，等几秒钟后松手。自己的电脑IP设置为自动获取，在浏览器登陆  http://192.168.1.1  就可以了。

