# ubuntu 使用笔记

## 双系统安装

###　分区
sdd + hdd win10+ubuntu 安装分区

\ 根目录可放在sdd中，也可放在hdd中。一般20-20Gb
\boot 放sdd中，500MB即可。
\home hdd中，随情况而定。
\swap 可要可不要。
安装引导的设备选择　\boot　即可。

### 引导
在win10 中用easybcd添加引导条目。同样选择\boot所在的分区。

## 安装完成后的事情
0. 更换国内源镜像
清华比较快。

1. 删除libreoffice

libreoffice虽然是开源的，但是Java写出来的office执行效率实在不敢恭维，装完系统后果断删掉

sudo apt-get remove libreoffice-common

2. 删除Amazon的链接
	
sudo apt-get remove unity-webapps-common


3. 删掉基本不用的自带软件（用的时候再装也来得及）

sudo apt-get remove thunderbird totem rhythmbox empathy brasero simple-scan gnome-mahjongg aisleriot gnome-mines cheese transmission-common gnome-orca webbrowser-app gnome-sudoku landscape-client-ui-install
 
sudo apt-get remove onboard deja-dup 

4. 安装Vim

sudo apt-get install vim

5. 安装搜狗拼音
安装 fcitx,可以在商店安装。
下载安装包，并安装。
设置中将键盘布局改为fcitx，注销系统，打开fcitx　config 选择搜狗拼音。


## 命令记录

>sudo dpkg -i (安装包)

>删除非空文件夹　rm -rf (folder)

>移动文件　cp (filename1) (filename2)

>git 配置用户名与邮箱　git config --global user.name user.email

>git config --list

>apt-get purge / apt-get --purge remove 
删除已安装包（不保留配置文件)。 
如软件包a，依赖软件包b，则执行该命令会删除a，而且不保留配置文件

>apt-get autoremove 
删除为了满足依赖而安装的，但现在不再需要的软件包（包括已安装包），保留配置文件。

>apt-get remove 
删除已安装的软件包（保留配置文件），不会删除依赖软件包，且保留配置文件。

>apt-get autoclean 
APT的底层包是dpkg, 而dpkg 安装Package时, 会将 *.deb 放在 /var/cache/apt/archives/中，apt-get autoclean 只会删除 /var/cache/apt/archives/ 已经过期的deb。

>apt-get clean 
使用 apt-get clean 会将 /var/cache/apt/archives/ 的 所有 deb 删掉，可以理解为 rm /var/cache/apt/archives/*.deb。


## vi/vim学习