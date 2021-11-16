# novaspirit's conky theme

made by Novaspirit Tech on YouTube, modified by Botspot

![screenshot](https://github.com/ryanfortner/conky-rpi/raw/main/conky_novaspirit/ss.png?raw=true)

## To Install:

```
sudo apt install -y conky
wget -O ~/.conkyrc https://github.com/ryanfortner/conky-rpi/raw/main/conky_novaspirit/conkyrc
```

To make it autostart on boot, create a file at `~/.config/autostart/conky.desktop` and place this code into it:
```
mkdir -p ~/.config/autostart
[Desktop Entry]
Name=Conky
Type=Application
Exec=bash -c 'sleep 5;conky -q -d'
Terminal=false
Comment=system monitoring tool.
Categories=Utility;
```

## To uninstall:

    sudo apt purge conky
    rm ~/.conkyrc ~/.config/autostart/conky.desktop

### Note about the network readout:
By default, this conky configuration is hard-coded to use the `eth0` network interface. If you are using WiFi, this needs changing before the network readout will work. In [the Pi-Apps installation script](https://github.com/Botspot/pi-apps/blob/master/apps/Conky/install), the `.conkyrc` file is edited if WiFi is detected.  
The commands used to accomplish this is provided below, for your convenience:
```
#change eth0 to wlan0 in conky config if user is currently using WiFi
interface="$(ip addr | awk '/state UP/ {print $2}' | tr -d ':' | head -n 1)"
if [ ! -z "$interface" ];then
  sed -i "s/eth0/$interface/g" ~/.conkyrc
fi
```
I suppose if you installed conky manually, you can run the above code in your terminal. (Or you could just edit the `.conkyrc` file.)