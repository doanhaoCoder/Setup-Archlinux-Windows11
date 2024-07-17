# Setup-Archlinux-Windows11
 
=====SETUP=====
#kiểm tra phân vùng
lsblk

#phân vùng ổ cứng
cfdisk /dev/X (X là ổ cứng)
//boot(512MB-efi system), 
//root(40-80GB-linux filesystem), 
//home(phần còn lại-linux firesystem). 
//thêm 1 phân vùng swap nếu cần.

#định dạng phân vùng 
mkfs.fat -F32 /dev/sda1(boot)
mkfs.ext4 /dev/sda2
mkfs.ext4 /dev/sda3

#check connect internet
ping google.com
#connect wlan
iwctl
device list
station wlan0(divece) scan
station wlan0 get-networks
station wlan0 connect "Name of Network/WiFi"
ping google.com

#setup
archinstall 
//tới đây dùng giao điện để cài đặt

#connect wlan
nmtui

=====TOOL=====

//gõ tiếng việt
#fcitx5 unikey
pacman -S fcitx5 fcitx5-qt fcitx5-gtk fcitx5-unikey kcm-fcitx5

nano /etc/environment

GTK_IM_MODULE=fcitx
QT_IM_MODULE=fcitx
XMODIFIERS=@im=fcitx

//duyệt file 
pacman -s dolphin kio-admin
