# raspi-notebook
raspi notebook

1. 树莓派准备工作（Prepare）：
  1). System Image
  官方系统下载：https://www.raspberrypi.org/downloads/raspbian/
  
  目前最新版本，推荐使用种子下载，如：
  https://downloads.raspberrypi.org/raspbian_full/images/raspbian_full-2019-07-12/2019-07-10-raspbian-buster-full.zip.torrent
 
  百度网盘分享：
  链接: https://pan.baidu.com/s/1K2vxHA1DJhQUFe2c42Oruw 提取码: ybgp

  2). SD Card Format
  Note ： 推荐SD卡格式化为FAT32  
  a. guiformat
  https://www.downloadbound.com/db/guiformat.exe/

  b. rufus
  http://rufus.ie/

  3). Write System Image
  a. Win32DiskImager
  https://sourceforge.net/projects/win32diskimager/files/
 
2. 树莓派第一次启动 (Start)
  1). 修改第一次开机使用的IP地址 
  烧写好系统镜像到SD卡后，不弹出SD卡，修改SD卡根目录下的cmdline.txt, 在文件最前面增加ip=192.168.88.100 （Note：IP地址为你的电脑所能访问的地址，第一次连接通常采用有线网络连接）

  2). 支持SSH登录
  支持SSH登录，只需要新建空文件ssh到SD卡（boot分区）的根目录下，启动完成后，采用第一步的IP即可登录到树莓派
  
  Note：官方系统镜像默认登录名和密码分别是：pi 和 raspberry

  3). 启动前的其他一些有用的配置
  a. USB鼠标配置 (解决鼠标延迟方法)
  打开cmdline文件后，在其末尾先加上空格后，再加上usbhid.mousepoll=0


3. 树莓派第一次使用 (First Use)
 1). 修改SSH登录启动提示语
 sudo vim /etc/motd 根据需要修改启动提示语

 2). 修改树莓派软件源
 国内用户推荐清华源或华中科技大学源，南方用户推荐华中科大源，修改步骤如下：
 sudo vim /etc/apt/sources.list
 
 修改后如下：
 #deb http://raspbian.raspberrypi.org/raspbian/ buster main contrib non-free rpi
 # #Uncomment line below then 'apt-get update' to enable 'apt-get source'
 #deb-src http://raspbian.raspberrypi.org/raspbian/ buster main contrib non-free rpi

 deb http://mirrors.ustc.edu.cn/raspbian/raspbian/ buster main contrib non-free rpi
 deb-src http://mirrors.ustc.edu.cn/raspbian/raspbian/ buster main contrib non-free rpi 

 修改源后执行update更新源：
 sudo apt-get update

 再执行以下命令更新软件包：
 sudo apt-get upgrade
 
4 . 树莓派一些工具推荐 (Recommend)
  1). raspap-webgui - 树莓派WIFI(支持AP和STA)管理工具
   https://github.com/billz/raspap-webgui
   


 
