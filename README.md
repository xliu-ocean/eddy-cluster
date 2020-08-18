# eddy-cluster
A small computer cluster served for the Ocean Circulation group

## tutorial for VNC viewer and Matlab

0. 需要用到的软件: (1) VNC viewer ([下载地址](https://www.realvnc.com/en/connect/download/viewer/windows/)); (2) 终端软件（如putty等,[putty下载地址](https://assets.ctfassets.net/0lvk5dbamxpi/4dkKbFS254RifqqGgOxXal/67819b284d7cf0c98e56c63bacaae320/putty-0.73-installer.msi)）

1. 第一次运行VNC viewer，请先用你的账号登陆到 EDDY 集群。比如，你可以按照[集群说明](https://github.com/rayliuxh/eddy-cluster/raw/master/manual_cluster_old.pdf)的方法，在Windows下利用putty登录到集群，或者在Linux/MacOS系统利用终端输入ssh username@172.16.10.133登录。

2. 登录后，在命令行输入
`vncserver -geometry 1920x1080` 注：1920x1080是你将要开启的虚拟桌面的分辨率大小，请根据自己的显示器分辨率来修改其中的数值。
上述命令执行后，会提示

`Starting applications specified in /data/home/username/.vnc/xstartup`

`Log file is /data/home/username/.vnc/node100:1.log`

则说明已经开启一个远程虚拟桌面，桌面的序号为:1 (请记下这个数字，下面会用到)。
注：如果第一次运行，可能需要输入密码，这个密码可以按照自己的喜好设置并记住即可。

3. 打开vnc viewer 软件，在最上端的地址栏输入
`172.16.10.133:5901`  注：冒号后的“5901”取决于你刚才运行vncserver时系统提示的数字“:N”，应为5900+N。如提示为":3"，则输入地址时，冒号后为"5903"。
然后在提示界面点击“continue”后，输入第一次运行vncserver时设置的密码（不是你的账户密码），即可打开虚拟桌面。虚拟桌面一般为Redhat linux系统。

4. 在虚拟桌面空白处点击右键，然后在弹出菜单里点击“open terminal”即可在虚拟桌面中打开一个终端。在打开的终端内输入`matlab &`，即可打开matlab的界面。
