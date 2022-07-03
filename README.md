# Ubuntu_22.04LTS
What to do when after installing Ubuntu 22.04LTS

## Update to latest version:
```
sudo apt update
sudo apt full-upgrade -y
sudo apt autoremove -y
```

## Enable Access to serial/usb port:
```
sudo usermod -a -G dialout $USER  
reboot
```

## Some Basic Programs:
```
sudo apt install -y git telegram-desktop pinta gimp geany vlc fritzing
```

## Some Extra Programs:
```
sudo apt install -y rpi-imager gparted putty filezilla kicad dia handbrake brasero solaar 
```

## 3. Party Programs:
### Visual Studio Code:
Kilde: [Code editing. Redefined.](https://code.visualstudio.com/)
* Get Code from here: [Visual Studio Code Download](https://code.visualstudio.com/Download)  
* Visual Studio Code is a lightweight but powerful source code editor which runs on your desktop and is available for Windows, macOS and Linux. It comes with built-in support for JavaScript, TypeScript and Node.js and has a rich ecosystem of extensions for other languages and runtimes (such as C++, C#, Java, Python, PHP, Go, .NET). Begin your journey with VS Code with these introductory videos.  

Download file an install it with:
```
sudo dpkg -i ~/Hentet/code_1.68.1-1655263094_amd64.deb
```

### OBS-Studio:
Kilde:
* [OBS Studio](https://obsproject.com/download#linux)
  * Gratis, Open Source-software til videooptagelse og live streaming.  
* YouTube Videos:
  * [Optag din Computerskærm med OBS Studio | Gratis](https://www.youtube.com/watch?v=bDcAStFrfCk)  
  * [Use Obs To Record YouTube Videos](https://www.youtube.com/watch?v=F1cCSLrOjog)
  * [The BEST Way to Live Stream With A Guest with OBS Studio](https://www.youtube.com/watch?v=iJ1_ZplBFoU)
  * [Obs Live Stream Tutorial - Add a guest to your Live Stream!](https://www.youtube.com/watch?v=g_TLoeNgZxs)  

```
sudo apt install -y qtwayland5
sudo apt install -y obs-studio
```

### Key-mon:
Kilde: 
* Download from Here: [Scott Kirkwood Key-mon releases:](https://github.com/scottkirkwood/key-mon/releases)  
* A screencast utility that displays your keyboard and mouse status  
Key-mon is useful for teaching since it shows the current status of your keyboard and mouse and you use them in another application. No longer do you need to say 'Now I'm pressing the Ctrl-D key', your students can just see the keystroke for themselves.  

Install it with:
```
sudo apt install -y python3-xlib
sudo dpkg -i ~/Hentet/keymon_1.20-1_all.deb
```

### Oracle VM VirtualBox:
Kilde: 
* VirtualBox is a general-purpose full virtualizer for x86 hardware, targeted at server, desktop and embedded use.

[Download VirtualBox for Linux Hosts here:](https://www.virtualbox.org/wiki/Linux_Downloads) - **Select Ubuntu 22.04**

```
sudo apt install -y libqt5opengl5
sudo dpkg -i ~/Hentet/virtualbox-6.1_6.1.34-150636.1_Ubuntu_jammy_amd64.deb
```

#### VirtualBox Extension Pack:
* VirtualBox 6.1.34 Oracle VM VirtualBox Extension Pack
* Support for USB 2.0 and USB 3.0 devices, VirtualBox RDP, disk encryption, NVMe and PXE boot for Intel cards. See this chapter from the User Manual for an introduction to this Extension Pack. The Extension Pack binaries are released under the VirtualBox Personal Use and Evaluation License (PUEL). Please install the same version extension pack as your installed version of VirtualBox.

[Download VirtualBox 6.1.34 Oracle VM VirtualBox Extension Pack](https://download.virtualbox.org/virtualbox/6.1.34/Oracle_VM_VirtualBox_Extension_Pack-6.1.34.vbox-extpack)

Start virtualBox and the start VirtualBox Extension Pack it will then start installation in VirtualBox.


## AppImage:
Kilde: 
* [AppImageKit](https://github.com/AppImage/AppImageKit/wiki)

An AppImage is a downloadable file for Linux that contains an application and everything the application needs to run (e.g., libraries, icons, fonts, translations, etc.) that cannot be reasonably expected to be part of each target system  

### Where to place my AppImages file:
* I place my AppImage file in the local folder:
  * ~/.local/bin
* I place my AppImage.desktop file in local folder:
  * ~/.local/share/applications
* I place my AppImage Icons in the local folder:
  * ~/.local/share/icons

The bin & icons folder may not exist so I create them
```
mkdir -p ~/.local/bin
mkdir -p ~/.local/share/icons
```

### How to set your $PATH 
Kilde: 
* [Opensource.com](https://opensource.com/article/17/6/set-path-linux)
* Telling your Linux shell where to look for executable files is easy, and something everyone should be able to do.
```
PATH="$PATH:$HOME/bin"
```
### AppImage Fuse:
Kilde:
* [ AppImage / AppImageKit /FUSE ](https://github.com/AppImage/AppImageKit/wiki/FUSE)
* AppImages require FUSE version 2 to run. Filesystem in Userspace (FUSE) is a system that lets non-root users mount filesystems.
Install FUSE

Many distributions have a working FUSE setup out-of-the-box. However if it is not working for you, you may need to install and configure FUSE manually.

For example, on Ubuntu (>= 22.04):

```
sudo apt-add-repository universe
sudo apt install libfuse2
reboot
```
### Download Appimage Programs:

* Get FreeCad here: [FreeCad](https://www.freecadweb.org/downloads.php)
* Get Ultimaker Cura here: [Cura](https://ultimaker.com/software/ultimaker-cura)
* get Audacity here: [Audacity](https://www.audacityteam.org/download/linux/)

Move files to ~/.local/bin:

```
mv ~/Hentet/*.AppImage ~/.local/bin
```

### Get Icons 

Icons for this program you can get from my Github page [My Icons](https://github.com/sekt1953/Ubuntu_22.04LTS/tree/main/local/share/icons)  

Save the png files in the folder ***~/.local/share/icons***

## AppImages Desktop Files:
### FreeCad_0.20.0.AppImage:
```
nano ~/.local/share/applications/FreeCad_0.20.0.desktop
```
Content of file:
```
[Desktop Entry]
Type=Application
Name=FreeCAD_0.20.0.App
Comment=FreeCAD_0.20.0
Categories=Graphics;Science;Engineering;
Icon=FreeCAD.png
Exec=FreeCAD-0.20.0-Linux-x86_64.AppImage
Terminal=false
Name[da_DK]=FreeCAD_0.20.0
MimeType=application/x-extension-fcstd;
StartupNotify=true
GenericName[da_DK]=CAD-program
```
To Save : [Ctrl]+o  
To Exit : [Ctrl]+w

### Ultimaker-Cura-5.0.0-linux.AppImage:
```
nano ~/.local/share/applications/Cura-5.0.0.desktop
```
Content of file:
```
[Desktop Entry]
Type=Application
Name=Ultimaker-Cura-5.0.0-linux
Comment=Ultimaker-Cura-5.0.0-linux
Icon=Cura.png
Exec=env LD_PRELOAD=/usr/lib/x86_64-linux-gnu/libstdc++.so.6 Ultimaker-Cura-5.0.0-linux.AppImage
Categories=Categories=Graphics;2DGraphics;3DGraphics;RasterGraphics;GTK;
Terminal=false
Name[da_DK]=Ultimaker-Cura-5.0.0-linux
StartupNotify=true
GenericName[da_DK]=CAD-program
```
To Save : [Ctrl]+o  
To Exit : [Ctrl]+w

### audacity-linux-3.1.3-x86_64.AppImage:
```
nano ~/.local/share/applications/audacity-linux-3.1.3-x86_64.desktop
```
Content of file:
```
[Desktop Entry]
Type=Application
Name=audacity-linux-3.1.3-x86_64
Comment=audacity-linux-3.1.3-x86_64
Categories=Graphics;Science;Engineering;
Icon=Audacity.png
Exec=audacity-linux-3.1.3-x86_64.AppImage
Terminal=false
Name[da_DK]=audacity-linux-3.1.3-x86_64
StartupNotify=true
```
To Save : [Ctrl]+o  
To Exit : [Ctrl]+w

### BalenaEtcher-1.7.9-x64.AppImage:
```
nano ~/.local/share/applications/balenaEtcher-1.7.9-x64.desktop
```
Content of file:
```
[Desktop Entry]
Type=Application
Name=balenaEtcher-1.7.9-x64.App
Comment=balenaEtcher-1.7.9-x64
Categories=Graphics;Science;Engineering;
Icon=Etcher-icon.png
Exec=balenaEtcher-1.7.9-x64.AppImage
Terminal=false
Name[da_DK]=balenaEtcher-1.7.9-x64
StartupNotify=true
GenericName[da_DK]=balenaEtcher
```
To Save : [Ctrl]+o  
To Exit : [Ctrl]+w


### [How to run an AppImage](https://discourse.appimage.org/t/how-to-run-an-appimage/80) 

Before you can run an AppImage, you need to make it executable. This is a Linux security feature. There are three main ways to make an AppImage executable:

```
chmod a+x ~/.local/bin/*.AppImage
chmod a+x ~/.local/share/applications/*.desktop
```
# WayLand:
## How to enable/disable Wayland on Ubuntu 22.04 Desktop
Some programs can not run on  Waylan but nead X

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




# Old Video Recorder that not run Wayland:
## Kdenlive:
Kilde: 
* [Linux Shout](https://www.how2shout.com/linux/3-ways-to-install-kdenlive-on-ubuntu-22-04-lts-jammy/)
* Kdenlive is an open source video editor. The project was started around 2003. Kdenlive is built on Qt and the KDE Frameworks libraries. Most of the video processing is done by the MLT Framework, which relies on many other open source projects like FFmpeg, frei0r, movit, ladspa, sox, etc…
```
sudo apt install -y kdenlive
```

## Simple Screen Recorder:
Kilde: 
* [Linux Shout](https://www.how2shout.com/linux/install-simplescreenrecorder-in-ubuntu-20-04-lts-to-record-screen/)
* [Linuxhint](https://linuxhint.com/install_simple_screen_recorder_ubuntu/)
* SimpleScreenRecorder is a Linux program that I've created to record programs and games. There were already a few programs that could do this, but I wasn't 100% happy with any of them, so I created my own.  
My original goal was to create a program that was just really simple to use, but as I was writing it I started adding more and more features, and the result is actually a pretty powerful program. It's 'simple' in the sense that it's easier to use than ffmpeg/avconv or VLC, because it has a straightforward user interface.
```
sudo apt install -y simplescreenrecorder 
```

