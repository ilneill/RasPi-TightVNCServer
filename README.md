## Raspberry Pi TightVNC Server Autostart Script

An easy script to ensure the TightVNC Server autostarts when the Raspberry Pi boots up.

Tested on a few Raspberry Pi Model B+s (Wheezy) and a Raspberry Pi 2 (Jessie) too.

### Why?
It ensures I have reliable headless access to my Raspberry Pis, even after reboots.

### Is it useful?
Yes, as it allows me to easily and reliably access my Raspberry Pis, regardless of where they are located.

### Installation
Ensure the Raspberry Pi system is up to date:
```
sudo apt-get update
sudo apt-get upgrade
```
Install the TightVNC server software:
```
sudo apt-get install tightvncserver
```
Run TightVNC and set a password:
```
/usr/bin/tightvncserver
```
Test your Raspberry Pi access with a VNC client:
```
VNC://Raspberry.Pi.IP.Address:1
```
Put the TightVNC Server autostart script here:
```
/etc/init.d/tightvncserver
```
Sort the script ownership and permissions:
```
sudo chown root:root /etc/init.d/tightvncserver
sudo chmod 755 /etc/init.d/tightvncserver
```
Add the script to the default runlevels:
```
sudo update-rc.d tightvncserver defaults
```
Reboot to make sure it's all works:
```
sudo shutdown -r now
```
### Missing and ToDo
Nothing... unless something is spotted.

### Credits
Most of the Internet for help & inspiration.

### License
Public domain - do what you like.
