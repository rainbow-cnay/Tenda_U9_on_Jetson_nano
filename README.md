# Tenda_U9_on_Jetson_nano
编译的腾达U9 驱动

我刚买了Tenda U9，算比较便宜，在WIN系统上正常，速度还可以。但在JETSON NANO上没有驱动可用，驱动是为x86_64设计的。
直接编译不成功，我用非常笨拙的方法修改了下，编译成功，使用正常。
请参考 https://github.com/MingxuZhang/rtl8821cu 里的安装方法。重点是：

Plug your USB-wifi-adapter into your PC
If wifi can be detected, congratulations. If not, maybe you need to switch your device usb mode by the following steps in terminal:

find your usb-wifi-adapter device ID, like "0bda:1a2b", by type:
lsusb
switch the mode by type: (the device ID must be yours.)
sudo usb_modeswitch -KW -v 0bda -p 1a2b
It should work.

使用时要切换一下网卡的模式，才可工作。实际上可以用脚本，检测到此设备插入时，自动执行usb_modeswitch。

GITHUB我还不太会用，所以仅上传了文件，在这里：

https://github.com/rainbow-cnay/Tenda_U9_on_Jetson_nano

把文件放到rtl8821cu目录里，应该可以直接用 make install 安装。祝好运！

