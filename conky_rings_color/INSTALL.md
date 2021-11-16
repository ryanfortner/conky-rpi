# conky_rings_color

A stylish ring-shaped conky theme showing system statistics.

Thanks to [Botspot](https://github.com/Botspot), this variation contains colors.


### Screenshot
![screenshot](https://github.com/ryanfortner/conky-rpi/raw/main/conky_rings_color/conky_screenshot.png?raw=true)

### Installation
Install conky and lua50 package using `apt`
```
sudo apt-get update
sudo apt install conky-all lua50 -y
```
Download and install conky configuration file
```
wget -O ~/.conkyrc https://github.com/ryanfortner/conky-rpi/raw/main/conky_rings_color/conkyrc
```
Create fonts directory and install fonts
```
mkdir -p ~/.local/share/fonts
wget -O ~/fonts.tar.gz https://github.com/ryanfortner/conky-rpi/raw/main/conky_rings_color/fonts.tar.gz
cd ~/ && tar -xvf fonts.tar.gz && mv *.ttf ~/.local/share/fonts
rm .uuid
wget -O ~/.conky_rings.lua https://github.com/ryanfortner/conky-rpi/raw/main/conky_rings_color/conky_rings.lua
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
