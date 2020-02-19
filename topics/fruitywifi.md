# Fruity WiFi
kali linux has a lot of tools that can be used via ssh. But what if we wanted to do more. Do you know that we can use a 3g/4g dongle with the raspberry pi and turn it into a remote hacking device?

Yes, it is possible!

all we need is fruity wifi. (can also be done manually) . Fruity wifi gives us a web interface with which we can work along with a lot of tools for pentesters. For more info on FruityWifi visit their official [site](http://fruitywifi.com/)

## installation

You need a Raspbian, Pwnpi or Kali Linux version to use this script.
 
Download the zip file
```
wget https://github.com/xtr4nge/FruityWifi/archive/master.zip
```
Unzip the file and run `install-FruityWiFi.sh`
```
cd master
./install-FruityWiFi.sh
```
This script will install all the dependencies and setups
**Done.**

Go to http://localhost:8000 (for http)
Go to https://localhost:8443 (for https)

**user:** `admin` 
**pass:** `admin`

![fruitywifi](http://fruitywifi.com/img/001.png)

.
![fruitywifi config](http://fruitywifi.com/img/002.png)



[<- cd ..](https://kalipiconf.tk/list)

[<- cd /home/](https://kalipiconf.tk/)
