# Conky Graph theme
###### DO NOT CREATE ISSUES IN THIS REPOSITORY, ISSUES ARE EXPECTED ON OTHER HARDWARE, CHANGES MIGHT BE NECESSARY FOR YOUR USE CASE
I did not make the original configuration. It is a fork modified to work with Raspberry Pies.

### Screenshot
![image](https://user-images.githubusercontent.com/28309837/127056441-4869d168-72f2-4721-913a-63f4abbd9bc4.png)

### Installation
```
# install fonts
mkdir setup-fonts
cd setup-fonts
wget https://github.com/ryanfortner/conky-configuration/raw/main/conky_graphs/resources/fonts/JetBrains_Mono.zip
unzip JetBrains_Mono.zip && mv *.ttf ~/.local/share/fonts/
rm -rf *
wget https://github.com/ryanfortner/conky-configuration/raw/main/conky_graphs/resources/fonts/Krona_One.zip
unzip Krona_One.zip && mv *.ttf ~/.local/share/fonts/
cd .. && rm -rf setup-fonts

# setup the actual theme, and install conky, make sure to remove old .conkyrc file if there is one
sudo apt-get update && sudo apt-get install conky-all -y
wget -O ~/.conkyrc https://github.com/ryanfortner/conky-configuration/raw/main/conky_graphs/conkyrc

# add to autostart so it will start on boot
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

### Credits
[ZvonimirKucis](https://github.com/ZvonimirKucis/conky) and [Abadillo](https://github.com/abadillo/files)
