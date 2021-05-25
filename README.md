# conky-rpi
Conky is a desktop widget that can display system stats such as CPU, Disk, Network usage and more.

This has only been tested on TwisterOS and Raspberry Pi OS (both 32bit).


### Screenshot
![screenshot](https://i.imgur.com/gLdUnBf.png)

### Installation
Install conky and lua50 package using `apt`
```
sudo apt-get update
sudo apt install conky-all lua50 -y
```
Download and install conky configuration file
```
wget -O ~/.conkyrc https://github.com/chunky-milk/conky-rpi/raw/main/conkyrc
```
Create fonts directory and install fonts
```
mkdir -p ~/.local/share/fonts
wget -O ~/fonts.tar.gz https://github.com/chunky-milk/conky-rpi/raw/main/fonts.tar.gz
cd ~/ && tar -xvf fonts.tar.gz && mv *.ttf /home/pi/.local/share/fonts
rm .uuid
wget -O ~/.conky_rings.lua https://github.com/chunky-milk/conky-rpi/raw/main/conky_rings.lua
```
Add conky to autostart so it will start on boot
```
mkdir -p ~/.config/autostart
echo -n '' > ~/.config/autostart/conky.desktop
echo "[Desktop Entry]
Name=Conky
Type=Application
Exec=bash -c 'sleep 5;conky -q -d -p 3'
Terminal=false
Comment=system monitoring tool.
Categories=Utility;" > ~/.config/autostart/conky.desktop
```
*Now, you can reboot and it should launch.*
