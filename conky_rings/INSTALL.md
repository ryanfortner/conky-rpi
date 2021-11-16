# conky_rings

A stylish ring-shaped conky theme showing system statistics.

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
wget -O ~/.conkyrc https://github.com/ryanfortner/conky-rpi/raw/main/conky_rings/conkyrc
```
Create fonts directory and install fonts
```
mkdir -p ~/.local/share/fonts
wget -O ~/fonts.tar.gz https://github.com/ryanfortner/conky-rpi/raw/main/conky_rings/fonts.tar.gz
cd ~/ && tar -xvf fonts.tar.gz && mv *.ttf ~/.local/share/fonts
rm .uuid
wget -O ~/.conky_rings.lua https://github.com/ryanfortner/conky-rpi/raw/main/conky_rings/conky_rings.lua
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
Now, you can reboot and it should launch.
