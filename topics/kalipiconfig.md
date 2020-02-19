## Kalipi-config
Often times we do not use a screen on the pi. after installing kali I usually ssh into the pi for setup and running. Yes, having an hdmi or any other screen helps, and we can use vnc. the issue is when setting up the wifi or other settings. On raspbian we have raspi-config for this. In kali this option seems to be absent. the following option will help in the process - simply typing kalipi-config will bring up the setup menu with a lot of options.

**here is how to install:**
first we need to make sure we have all the needed requirements are installed
```
apt install whiptail parted lua5.1 alsa-utils psmisc libraspberrypi0 libraspberrypi-dev libraspberrypi-doc libraspberrypi-bin
``` 
then we download the file and move it into the `/usr/local/bin/` folder so that we can use the command from anywhere.
```
wget -O /usr/local/bin/kalipi-config https://raw.githubusercontent.com/Re4son/RPi-Tweaks/master/kalipi-config/kalipi-config 
```
we then give proper permissions to the file using `chmod`
```
chmod 755 /usr/local/bin/kalipi-config
```
to run, type in
```
kalipi-config
```
![screenshot of kalipi-config](https://camo.githubusercontent.com/58332c97bd193375a04f11b49c904bec65a72456/68747470733a2f2f726534736f6e2d6b65726e656c2e636f6d2f77702d636f6e74656e742f75706c6f6164732f6b616c6970692d636f6e6669672e706e67)

As you can see in the screenshot there are a ton of options available. from setting up the wireless interface to autologin on startup. these options will always come in handy and we do not need to search around the web each time we setup something.

link to **[original github post](https://github.com/Re4son/RPi-Tweaks/tree/master/kalipi-config)**

[<- cd ..](https://kalipiconf.tk/list)

[<- cd /home/](https://kalipiconf.tk/)
