# Ubuntu_22.04LTS
What to do when instaled Ubuntu 22.04LTS


```
sudo apt update
sudo apt full-upgrade -y
```


```
# opret directory til dine bin filer
mkdir -p ~/.local/bin
mkdir -p ~/.local/share/icons
PATH="$PATH:$HOME/bin"
```


```
sudo apt install -y pinta geany gimp git

```


```
# giv default bruger adgang til serial port
sudo usermod -a -G dialout $USER  
reboot
```


