# Ubuntu_22.04LTS
What to do when after installing Ubuntu 22.04LTS

## Update to latest version:
```
sudo apt update
sudo apt full-upgrade -y
```

## Basic Program:
```
sudo apt install -y pinta gimp geany git telegram-desktop 
```

## How to enable/disable Wayland on Ubuntu 22.04 Desktop
Kilde: 
* [LinuxConfig.org](https://linuxconfig.org/how-to-enable-disable-wayland-on-ubuntu-22-04-desktop)  
*  [WayLand](https://wayland.freedesktop.org/)  
  Wayland is intended as a simpler replacement for X, easier to develop and maintain. GNOME and KDE are expected to be ported to it.

* [GNOME Display Manager (gdm3):](https://askubuntu.com/questions/829108/what-is-gdm3-kdm-lightdm-how-to-install-and-remove-them)  
gdm3 is the successor of gdm which was the GNOME display manager. The newer gdm3 uses a minimal version of gnome-shell, and provides the same look and feel of as GNOME3 session. Is the Canonical choice since Ubuntu 17.10. You can install it with:
```
sudo nano /etc/gdm3/custom.conf
```
Within this file, look for the line that says #WaylandEnable=false. You can uncomment this line and either set it to true or false, depending on whether you want Wayland enabled or not.  
* Enable Wayland:
```
WayLandEnable=true
```
* Or disable Wayland:
```
WayLandEnable=false
```
After you have made the desired changes, save this file and exit it. You will need to restart GDM3 or reboot your Ubuntu 22.04 desktop for the changes to take effect.
```
sudo systemctl restart gdm3
```

## Access to serial port:
```
sudo usermod -a -G dialout $USER  
reboot
```

## Visual Studio Code:
Kilde: 
* [Download Visual Studio Code](https://code.visualstudio.com/Download)  

Download file an install it with:
```
sudo dpkg -i code_1.68.1-1655263094_amd64.deb
```

## Telegram:
Kilde: [Linuxhint](https://linuxhint.com/install-telegram-desktop-messenger-linux/)
```
sudo apt install -y telegram-desktop 
```

## Kdenlive:
Kilde: 
* [Linux Shout](https://www.how2shout.com/linux/3-ways-to-install-kdenlive-on-ubuntu-22-04-lts-jammy/)
```
sudo apt install -y kdenlive
```

## Simple Screen Recorder:
Kilde: 
* [Linux Shout](https://www.how2shout.com/linux/install-simplescreenrecorder-in-ubuntu-20-04-lts-to-record-screen/)
* [Linuxhint](https://linuxhint.com/install_simple_screen_recorder_ubuntu/)
```
sudo apt install -y simplescreenrecorder 
```

## Key-mon:
Kilde: 
* [Scott Kirkwood Key-mon releases:](https://github.com/scottkirkwood/key-mon/releases)  
* A screencast utility that displays your keyboard and mouse status  
Key-mon is useful for teaching since it shows the current status of your keyboard and mouse and you use them in another application. No longer do you need to say 'Now I'm pressing the Ctrl-D key', your students can just see the keystroke for themselves.  


Download file and install it with:
```
sudo dpkg -i keymon_1.20-1_all.deb
```

## AppImage:
```
# opret directory til dine bin filer
mkdir -p ~/.local/bin
mkdir -p ~/.local/share/icons
PATH="$PATH:$HOME/bin"
```

### FreeCad_0.20.0.AppImage

### Ultimaker-Cura-5.0.0-linux.AppImage

### audacity-linux-3.1.3-x86_64.AppImage

