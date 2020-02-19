# Wifite.
The main purpose of kali on raspberry pi is to do pentesting on wi-fis (atleast in my case). Cracking a wifi can be a lot of work as we need to use a lot of tools to crack one. We can use specially made tools like *pixie-dust* to crack a wps enabled network or capture a handshake and try a wordlist. There are a lot of ways for this.

Wifite is an automated tool for this.

It uses a collection of different tools and helps in cracking that wifi. See *derv82*'s [github page](https://github.com/derv82/wifite2) to know more about the tool.

here is how to install Wifite

first we clone the git repository
```
git clone https://github.com/derv82/wifite2.git 
```
move into the wifite folder
```
cd wifite2 
```
run the python file *setup.py* with argument install
```
python setup.py install 
```
basically this is all there is to do. we can run `wifite` to run wifite and it will start monitor mode a n start scanning for devices. But as we run we can see that it says most of the needed tools are missing. Check which of these are missing and install accordingly.

**reaver**
```
apt install reaver 
```
**bully**

```
apt install bully 
```
**pyrit**
```
apt install pyrit 
```
**macchanger** 
```
apt install macchanger 
```
after install it will ask if you want to change the mac id automatically. its your choice really. choosing yes is a more secure option but this will result in the device having a different mac each time i connect to the wifi. this makes it harder to detect. I usually select *no* for the convinience

**hcxdumptool**
```
apt install hcxdumptool 
```
**hashcat** 
 ```
 git clone https://github.com/hashcat/hashcat.git 
 cd hashcat 
 make
 make install 
```
**hcxcaptools(hcxtools)**
 ```
 git clone https://github.com/ZerBea/hcxtools 
 apt install libssl-dev 
 apt install libcurl4-gnutls-dev 
 cd hcxtools/ 
 make 
 make install
 ```

**Cracking WPS PIN using `reaver`'s Pixie-Dust attack, then fetching WPA key using `bully`:** ![reaver and bully](https://camo.githubusercontent.com/f42cc52be78e6cf23a93ecae7dda9799660fe87b/68747470733a2f2f692e696d6775722e636f6d2f51354b534462672e676966)

**Cracking WPA key using PMKID attack:**
![Cracking WPA key using PMKID attack](https://camo.githubusercontent.com/1ac7a9a3b31777f65e7350c5b1d9c63d3cfea1b4/68747470733a2f2f692e696d6775722e636f6d2f4352386f4f70302e676966)
**Decloaking & cracking a hidden access point (via the WPA Handshake attack):**
![Decloaking & cracking a hidden access point (via the WPA Handshake attack)](https://camo.githubusercontent.com/d9040281a0976ab2da3da6dc0f1c96850cc93cfc/68747470733a2f2f692e696d6775722e636f6d2f4636565068626d2e676966)

**Cracking a pre-captured handshake using John The Ripper (via the `--crack` option)**
![Cracking a pre-captured handshake using John The Ripper (via the --crack option)](https://camo.githubusercontent.com/bde1a4a0e04100ea6aaa0955928b357be43bd9c7/68747470733a2f2f692e696d6775722e636f6d2f69486366436a702e676966)


[<- cd ..](https://kalipiconf.tk/list)

[<- cd /home/](https://kalipiconf.tk/)
