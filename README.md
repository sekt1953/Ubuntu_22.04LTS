# Ubuntu_22.04LTS

## Se denne Video: [Windows 11 Must Be Stopped - A Veteran PC Repair Shop Owner's Dire Warning - Jody Bruchon](https://www.youtube.com/watch?v=LcafzHL8iBQ)

# What to do when after installing Ubuntu 22.04LTS

## Update to latest version

```code
sudo apt update && sudo apt full-upgrade -y && sudo apt autoremove -y
```

### some snap firefox problem

```code
sudo killall firefox && sudo snap refresh firefox
```

## Enable Access to serial/usb port

```code
sudo usermod -a -G dialout $USER  
```

```code
reboot
```

## Some Basic Programs

```code
sudo apt install -y git geany pinta gimp vlc  
```

## Some Extra Programs

```code
sudo apt install -y telegram-desktop rpi-imager gparted putty filezilla fritzing kicad dia handbrake brasero solaar
```

## LibreOffice-Base

Ubuntu 22,04 kommer ikke med libreoffice-base preinstaleret, jeg forstår ikke denne beslutning, Men her er hvordan den skal instaleres.
Her er en link til en ældre men god samling af [YouTube Videoer om brugen af LibreOffice-Base](https://www.youtube.com/playlist?list=PLy7Kah3WzqrEerJ0VPNWVaR4CYHMr4wmV)

 ```code
 sudo apt install -y libreoffice-base
 ```

## Change to X11 from Wayland

```code
sudo nano /etc/gdm3/custom.conf
```

Within this file, look for the line that says #WaylandEnable=false. You can uncomment this line and either set it to true or false, depending on whether you want Wayland enabled or not.  

* Disable Wayland:

```text
WayLandEnable=false
```

To Save : [Ctrl]+[o]  
To Exit : [Ctrl]+[w]

After you have made the desired changes, save this file and exit it. You will need to restart GDM3 or reboot your Ubuntu 22.04 desktop for the changes to take effect.

```code
sudo systemctl restart gdm3
```

# 3. Party Programs  

## dpkg

* The Debian Package (dpkg) is a Linux management low-level tool as compared to APT. It is used to perform different operations such as installing, updating or removing the .deb packages. The .deb is an extension for the Linux Debian software packages and their derivatives.

This article explain in a nice way how to install from commandline [How to let dpkg Install Dependencies Automatically](https://linuxhint.com/install-dpkg-dependencies-automatically/), read if you ran into problems.

## Visual Studio Code

Kilde: [Code editing. Redefined.](https://code.visualstudio.com/)

* Get Code from here: [Visual Studio Code Download](https://code.visualstudio.com/Download)  
* Visual Studio Code is a lightweight but powerful source code editor which runs on your desktop and is available for Windows, macOS and Linux. It comes with built-in support for JavaScript, TypeScript and Node.js and has a rich ecosystem of extensions for other languages and runtimes (such as C++, C#, Java, Python, PHP, Go, .NET). Begin your journey with VS Code with these introductory videos.  

Download file an install it with:
NB!!! Check you download version number and replace x.y-z in the command.

```code
sudo dpkg -i ~/Hentet/code_1.xx.y-zzzzzzzzzz_amd64.deb
```

## OBS-Studio

Kilde:

* [OBS Studio](https://obsproject.com/download#linux)
  * Gratis, Open Source-software til videooptagelse og live streaming.  
* YouTube Videos:
  * [Optag din Computerskærm med OBS Studio | Gratis](https://www.youtube.com/watch?v=bDcAStFrfCk)  
  * [Use Obs To Record YouTube Videos](https://www.youtube.com/watch?v=F1cCSLrOjog)
  * [The BEST Way to Live Stream With A Guest with OBS Studio](https://www.youtube.com/watch?v=iJ1_ZplBFoU)
  * [Obs Live Stream Tutorial - Add a guest to your Live Stream!](https://www.youtube.com/watch?v=g_TLoeNgZxs)  
  * [OBS University...Sort Of](https://www.youtube.com/playlist?list=PLT3XqaN4XtC0JbI5ZQwyJqkktrd-ChDE8)

```code
sudo apt install -y qtwayland5 && sudo apt install -y obs-studio
```

## Key-mon

Kilde:

* Download from Here: [Scott Kirkwood Key-mon releases:](https://github.com/scottkirkwood/key-mon/releases)  
* A screencast utility that displays your keyboard and mouse status  
Key-mon is useful for teaching since it shows the current status of your keyboard and mouse and you use them in another application. No longer do you need to say 'Now I'm pressing the Ctrl-D key', your students can just see the keystroke for themselves.  

NB! I can only get et to work with X11 not wtth WayLand, [see here](#wayland) how to change from WayLand to X11

Install it with:

```code
sudo apt install -y python3-xlib && sudo dpkg -i ~/Hentet/keymon_1.20-1_all.deb
```

## Oracle VM VirtualBox

Kilde:

* VirtualBox is a general-purpose full virtualizer for x86 hardware, targeted at server, desktop and embedded use.

[Download VirtualBox for Linux Hosts here:](https://www.virtualbox.org/wiki/Linux_Downloads) - **Select Ubuntu 22.04**

```code
sudo apt install -y libqt5opengl5
```

```code
sudo dpkg -i ~/Hentet/virtualbox-6.1_6.1.34-150636.1~Ubuntu~jammy_amd64.deb
```

### VirtualBox Extension Pack  

* VirtualBox 6.1.34 Oracle VM VirtualBox Extension Pack
* Support for USB 2.0 and USB 3.0 devices, VirtualBox RDP, disk encryption, NVMe and PXE boot for Intel cards. See this chapter from the User Manual for an introduction to this Extension Pack. The Extension Pack binaries are released under the VirtualBox Personal Use and Evaluation License (PUEL). Please install the same version extension pack as your installed version of VirtualBox.

[Download VirtualBox 6.1.34 Oracle VM VirtualBox Extension Pack](https://download.virtualbox.org/virtualbox/6.1.34/Oracle_VM_VirtualBox_Extension_Pack-6.1.34.vbox-extpack)

Start virtualBox and the start VirtualBox Extension Pack it will then start installation in VirtualBox.

### TeamViewer

Jeg bruger TeamViewer til fjern sopport, programmet kan hentest her: [teamviewer.com](https://www.teamviewer.com/en/)  
Klik [download for free] og Ubuntu, Debian - x86_64bit  
når programmet er hentet så installer det med Ubuntu's Software installer.

# AppImage  

Kilde:

* [AppImageKit](https://github.com/AppImage/AppImageKit/wiki)

An AppImage is a downloadable file for Linux that contains an application and everything the application needs to run (e.g., libraries, icons, fonts, translations, etc.) that cannot be reasonably expected to be part of each target system  

## Where to place my AppImages file  

* I place my AppImage file in the local folder:
  * ~/.local/bin
* I place my AppImage.desktop file in local folder:
  * ~/.local/share/applications
* I place my AppImage Icons in the local folder:
  * ~/.local/share/icons

The bin & icons folder may not exist so I create them

```code
mkdir -p ~/.local/bin && mkdir -p ~/.local/share/icons
```

## How to set your $PATH

Kilde:

* [Opensource.com](https://opensource.com/article/17/6/set-path-linux)
* Telling your Linux shell where to look for executable files is easy, and something everyone should be able to do.

```code
PATH="$PATH:$HOME/bin"
```

## AppImage Fuse

Kilde:

* [AppImage / AppImageKit /FUSE](https://github.com/AppImage/AppImageKit/wiki/FUSE)
* AppImages require FUSE version 2 to run. Filesystem in Userspace (FUSE) is a system that lets non-root users mount filesystems.
Install FUSE

Many distributions have a working FUSE setup out-of-the-box. However if it is not working for you, you may need to install and configure FUSE manually.

For example, on Ubuntu (>= 22.04):

```code
sudo apt-add-repository universe && sudo apt install libfuse2
```

```code
reboot
```

## Download Appimage Programs

* Download FreeCad 0.20.1 here: [FreeCad](https://www.freecadweb.org/downloads.php)
* Download Ultimaker-Cura-5.1.1-linux-modern here: [Cura](https://ultimaker.com/software/ultimaker-cura)
* Download Audacity here: [Audacity](https://www.audacityteam.org/download/linux/)
* Download and unzip balenaEtcher: [balenaEtcher](https://www.balena.io/etcher/)

Move files to ~/.local/bin:

```code
mv ~/Hentet/*.AppImage ~/.local/bin  
```

## Get Icons

Icons for this program you can get from my Github page [My Icons](https://github.com/sekt1953/Ubuntu_22.04LTS/tree/main/local/share/icons)  

Save the png files in the folder ***~/.local/share/icons***

## AppImages Desktop Files

### FreeCad_0.20.1.AppImage

```code
nano ~/.local/share/applications/FreeCad_0.20.1.desktop
```

Content of file:

```text
[Desktop Entry]
Type=Application
Name=FreeCAD_0.20.1.App
Comment=FreeCAD_0.20.1
Categories=Graphics;Science;Engineering;
Icon=FreeCAD.png
Exec=FreeCAD_0.20-1-2022-08-20-conda-Linux-x86_64-py310.AppImage
Terminal=false
Name[da_DK]=FreeCAD_0.20.1
MimeType=application/x-extension-fcstd;
StartupNotify=true
GenericName[da_DK]=CAD-program
```

To Save : [Ctrl]+[o]  
To Exit : [Ctrl]+[w]

### Ultimaker-Cura-5.1.1-linux-modern.AppImage

```code
nano ~/.local/share/applications/Cura-5.1.1.desktop
```

Content of file:

```text
[Desktop Entry]
Type=Application
Name=Ultimaker-Cura-5.1.1-linux
Comment=Ultimaker-Cura-5.1.1-linux
Icon=Cura.png
Exec=Ultimaker-Cura-5.1.1-linux-modern.AppImage
Categories=Categories=Graphics;2DGraphics;3DGraphics;RasterGraphics;GTK;
Terminal=false
Name[da_DK]=Ultimaker-Cura-5.1.1-linux
StartupNotify=true
GenericName[da_DK]=CAD-program
```

To Save : [Ctrl]+[o]  
To Exit : [Ctrl]+[w]

### audacity-linux-3.1.3-x86_64.AppImage

```code
nano ~/.local/share/applications/audacity-linux-3.1.3-x86_64.desktop
```

Content of file:

```text
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

To Save : [Ctrl]+[o]  
To Exit : [Ctrl]+[w]

### BalenaEtcher-1.7.9-x64.AppImage

Se disse fejl medelse:

* [Etcher does not work on Ubuntu 22.04 and Linux Mint 21](https://forums.balena.io/t/known-issue-etcher-does-not-work-on-ubuntu-22-04-and-linux-mint-21/360557/3)  
* [GPU process isn't usable. Goodbye. #3639](https://github.com/balena-io/etcher/issues/3639#issuecomment-1153285345)

Denne linie virker for mig:

```code
Exec=balenaEtcher-1.7.9-x64.AppImage --disable-gpu-sandbox
```

Opret desktop fil:

```code
nano ~/.local/share/applications/balenaEtcher-1.7.9-x64.desktop
```

Content of file:

```text
[Desktop Entry]
Type=Application
Name=balenaEtcher-1.7.9-x64.App
Comment=balenaEtcher-1.7.9-x64
Categories=Graphics;Science;Engineering;
Icon=Etcher-icon.png
Exec=balenaEtcher-1.7.9-x64.AppImage --disable-gpu-sandbox
Terminal=false
Name[da_DK]=balenaEtcher-1.7.9-x64
StartupNotify=true
GenericName[da_DK]=balenaEtcher
```

To Save : [Ctrl]+[o]  
To Exit : [Ctrl]+[w]

### ESPHome-Flasher-1.4.0-Ubuntu-x64.exec

### NB!!! This program do not run under WayLand it have to run under X11, see more in Wayland chapter

Kilde: [releases section](https://github.com/esphome/esphome-flasher/releases)

```code
nano ~/.local/share/applications/ESPHome-Flasher-1.4.0-Ubuntu-x64.desktop
```

Content of file:

```text
[Desktop Entry]
Type=Application
Name=ESPHome-Flasher-1.4.0-Ubuntu-x64.exec
Comment=ESPHome-Flasher-1.4.0-Ubuntu-x64
Categories=Graphics;Science;Engineering;
Icon=EspHomeFlasher.png
Exec=ESPHome-Flasher-1.4.0-Ubuntu-x64.exec
Terminal=false
Name[da_DK]=ESPHome-Flasher-1.4.0-Ubuntu-x64
StartupNotify=true
```

To Save : [Ctrl]+[o]  
To Exit : [Ctrl]+[w]

### [How to run an AppImage](https://discourse.appimage.org/t/how-to-run-an-appimage/80)

Before you can run an AppImage, you need to make it executable. This is a Linux security feature. There are three main ways to make an AppImage executable:

```code
chmod a+x ~/.local/bin/*.AppImage
```

```code
chmod a+x ~/.local/share/applications/*.desktop
```

# WayLand  

## How to enable/disable Wayland on Ubuntu 22.04 Desktop

Some programs can not run on  Waylan but nead X

Kilde:

* [LinuxConfig.org](https://linuxconfig.org/how-to-enable-disable-wayland-on-ubuntu-22-04-desktop)  
* [WayLand](https://wayland.freedesktop.org/)  
  Wayland is intended as a simpler replacement for X, easier to develop and maintain. GNOME and KDE are expected to be ported to it.

* [GNOME Display Manager (gdm3):](https://askubuntu.com/questions/829108/what-is-gdm3-kdm-lightdm-how-to-install-and-remove-them)  
gdm3 is the successor of gdm which was the GNOME display manager. The newer gdm3 uses a minimal version of gnome-shell, and provides the same look and feel of as GNOME3 session. Is the Canonical choice since Ubuntu 17.10. You can install it with:

```code
sudo nano /etc/gdm3/custom.conf
```

Within this file, look for the line that says #WaylandEnable=false. You can uncomment this line and either set it to true or false, depending on whether you want Wayland enabled or not.  

* Enable Wayland:

```text
WayLandEnable=true
```

* Or disable Wayland:

```text
WayLandEnable=false
```

After you have made the desired changes, save this file and exit it. You will need to restart GDM3 or reboot your Ubuntu 22.04 desktop for the changes to take effect.

```code
sudo systemctl restart gdm3
```

# Old Video Recorder that not run Wayland

## Kdenlive

Kilde:

* [Linux Shout](https://www.how2shout.com/linux/3-ways-to-install-kdenlive-on-ubuntu-22-04-lts-jammy/)
* Kdenlive is an open source video editor. The project was started around 2003. Kdenlive is built on Qt and the KDE Frameworks libraries. Most of the video processing is done by the MLT Framework, which relies on many other open source projects like FFmpeg, frei0r, movit, ladspa, sox, etc…

```code
sudo apt install -y kdenlive
```

## Simple Screen Recorder

Kilde:

* [Linux Shout](https://www.how2shout.com/linux/install-simplescreenrecorder-in-ubuntu-20-04-lts-to-record-screen/)
* [Linuxhint](https://linuxhint.com/install_simple_screen_recorder_ubuntu/)
* SimpleScreenRecorder is a Linux program that I've created to record programs and games. There were already a few programs that could do this, but I wasn't 100% happy with any of them, so I created my own.  
My original goal was to create a program that was just really simple to use, but as I was writing it I started adding more and more features, and the result is actually a pretty powerful program. It's 'simple' in the sense that it's easier to use than ffmpeg/avconv or VLC, because it has a straightforward user interface.

```code
sudo apt install -y simplescreenrecorder 
```

# Other nice tools to have

## Octoprint for linux

I follow paukstelis guide see link below

* Youtube:
  * [Multiple OctoPrint instances FAST with Ubuntu/Linux](https://www.youtube.com/watch?v=1YINWQ5fNn0)  
  * [FAST multiple octoprint instances for OctoPi and Ubuntu](https://www.youtube.com/watch?v=J5VzI4AFav4&t=3s)

* GitHub:  
  * [paukstelis/octoprint_deploy](https://github.com/paukstelis/octoprint_deploy)

# Snap Problems

Kilde: [Ask Ubuntu](https://askubuntu.com/questions/1411623/cant-update-firefox-snap-on-22-04)

```text
 tried to update Firefox Snap (from 100 to 101):

sudo snap refresh firefox

but I got a message that an update was pending, but it could not update because Firefox was running an app, although I did close all Firefox windows and I couldn't find anything with pgrep firefox

After a reboot, the update command was working.

So, how do you update Firefox on Ubuntu 22.04 without restarting the system?
I received repeated messages that an update to Firefox was pending, but I ignored them because I didn't want to reboot yet. Closing Firefox didn't stop these messages from repeating, and neither did running sudo apt update & sudo apt upgrade. In my case only restarting Ubuntu worked. After rebooting Ubuntu the Firefox snap package was updated from 100 to 101 right away. – 
karel
 Jun 2 at 5:54
Even after rebooting, the update is not installed in my case. – 
MPi
 Jun 2 at 7:16
 ```

```text
 Answer

I had a similar issue, but I was simply being neglectful about closing Firefox.

However, I recommend using something like 

pkill firefox 
or 
killall firefox 

in the future to see if that'll close all instances of Firefox to stop it from complaining.
```

### Gammel Version Ultimaker-Cura-5.0.0-linux.AppImage

```code
nano ~/.local/share/applications/Cura-5.0.0.desktop
```

Content of file:

```text
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

