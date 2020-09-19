# Hackintosh-ASUS-GL552VW-FXPRO6300HQ-Clover Bootloader Configuration
这可以帮助您完美地运行macOS High Sierra & Mojave & Catalina（最高10.15.6 - 19G2021）  
由于Clover引导器暂不支持macOS 10.16 Big Sur，所以我考虑近期推出该机型的OpenCore引导器配置文件

This can help you run macOS High Sierra & Mojave & Catalina(10.15.6 - 19G2021 maximum)perfectly.  
Because the Clover bootloader cannot boot macOS 10.16 Big Sur successfully, I am considering launching the OpenCore bootloader configuration file for this model recently.

## 注意 & Attention
想要用这个EFI启动你的macOS，你需要做这几件事：  
  1.把你的UEFI固件版本升级为304版本  
  2.在UEFI设置中关闭Fast Boot, CSM Mode, Secure Boot  
  3.在UEFI中的Graphic Configuration菜单中把dvmt设置为256mb  
少了以上任意一条，你都无法启动系统或者某些驱动有问题  

To start your macOS with this EFI, you need to do a few things:  
   1. Upgrade your UEFI Firmware to version 304  
   2. Turn off Fast Boot, CSM Mode, Secure Boot in the UEFI settings  
   3. Set dvmt to 256mb in the Graphic Configuration menu in the UEFI  
Without any of the above, you cannot start the system or there are problems with some drivers  

## 联系我 & Contact me
__如果你有问题，可以在百度贴吧联系我（绿胡子大叔）或给我发邮件jonesbak@outlook.com 如果你在某个黑苹果群遇见我也可以直接问我，昵称一般是Elton11220，YJHuaa__  
__If you have problems, contact me with jonesbak@outlook.com__

## 关于转载 & About repost  
该项目仅供技术交流，请勿用于商业用途，转载请注明来源及原作者，请尊重我的劳动，谢谢！  
This project is only for technical communicating, please do not use it for commercial purposes, please indicate the source and original author for reprint, please respect my labor, thank you!

## 电脑配置 & The hardware configuration

Hardware | Detail
---------|----------
CPU      | Intel Core i5-6300HQ
IGPU     | HD530
EGPU     | Nvidia Geforce GTX960M(4G)
Wifi     | Boradcom 94350(DW1820A)/Atheros AW-NB182NF(AR9565 - the original wireless LAN adapter)
SSD      | SAMSUNG MZNLF128HCHP-00004
RAM      | SK HYNIX 8G*1 2133MHz
Display	 | BOE NV156FHM-N65(Original monitor AUO B156HTN03.6 is supported)
TouchPad | ELAN 1000
Sound    | Conexant 20751/2

该项目包括Clover v5.0 r5122（支持macOS Catalina）  
我将启动等待时间设置成了2秒，如果你想用这个配置来安装macOS，你可能需要进入clover界面后，按“o”键，然后在boot-args中添加“-v”，这样你就可以获得详细的错误信息

This project includes clover v5.0 r5122.(macOS Catalina Supported)  
I set the clover to wait for 2 second before booting automatically. If you want to use it for installing macOS,you may need to
press the "o" key after entering the clover interface,and then add "-v" in boot args so that you can get detailed error information.

## 显卡 & Graphics GPU
由于硬件问题和新版本macOS中缺乏驱动程序支持，macOS Mojave & Catalina不支持Nvidia GPU，此配置中我禁用了独立显卡

据我们所知，macOS Catalina和Mojave没有Nvidia显卡的驱动程序，因此您只能在这些系统上使用核显

如果要使用Nvidia显卡，你只能使用macOS High Sierra及以下版本，然后配置NVIDIA Webdriver

* [Nvidia WebDriver 下载](https://www.tonymacx86.com/Nvidia-drivers/)

注意：你可以尝试驱动GTX960m显卡，但是据我所知，clover不支持这款显卡的Optimus技术，所以未必有用  

-----------------------------------------------------------------------------------

The Nvidia GPU is not supported because of hardware differences and lack of driver support in the new version macOS.   

As far as we know, NVIDIA GPU do not have drivers to support them on macOS Catalina & Mojave, so you can only
use IGPU on these systems. 

If you want to use EGPU, you can only use macOS High Sierra and below,and then configure NVIDIA Webdriver.

* [Nvidia WebDriver Download](https://www.tonymacx86.com/nvidia-drivers/)

Note: You can try to drive the GTX960m graphics card, but as far as I know, clover does not support Optimus technology for this graphics card, so it may not work
