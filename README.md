#安装betterlockscreen
yay -S betterlockscreen

#配置
更新缓存的锁屏壁纸
betterlockscreen -u ~/Wallpapers/image.png --fx dim,pixel
更换锁屏壁纸及壁纸的样式
betterlockscreen -w pixel
锁屏,并设置锁屏桌面为模糊 变暗或者像素化
betterlockscreen -l blur 
或者
betterlockscreen -l dim
betterlockscreen -l pixel

#设置为服务，让系统在休眠或者挂起的时候会执行锁屏操作

# # move service file to proper dir (the aur package does this for you)
# 如果是yay安装则不用复制,已经放到指定目录中
# cp betterlockscreen@.service /usr/lib/systemd/system/
# enable systemd service
systemctl enable betterlockscreen@$USER
# disable systemd service
# systemctl disable betterlockscreen@$USER

# 让系统定时锁定屏幕并且在排除特定应用在使用过程中的锁屏，需要设置脚本中的程序
pacman -S xautolock

开机启动脚本中执行
xautolock -time 5  -locker "~/scripts/lockscreen.sh"

编辑脚本~/scripts/lockscreen.sh
排除不锁屏程序在焦点时不锁定屏幕。

