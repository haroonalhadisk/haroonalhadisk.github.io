# hashcatch

hashcatch is an automated hanshake capture tool. it captures all possible handshakes around the wifi adapter and saves the cap file. Which can be later used for cracking.

original link : [hashcatch](https://github.com/staz0t/hashcatch)

## installation

git clone:
```
git clone https://github.com/staz0t/hashcatch
```
move into the folder
```
cd hashcatch
```
run hashcatch as setup
```
./hashcatch --setup
```
this should start the setup process. in my case it presented me with the following error:
```
root@kali:~/hashcatch# ./hashcatch --setup

 __   __  _______  _______  __   __  _______  _______  _______  _______  __   __
|  | |  ||   _   ||       ||  | |  ||       ||   _   ||       ||       ||  | |  |
|  |_|  ||  |_|  ||  _____||  |_|  ||       ||  |_|  ||_     _||       ||  |_|  |
|       ||       || |_____ |       ||       ||       |  |   |  |       ||       |
|       ||       ||_____  ||       ||      _||       |  |   |  |      _||       |
|   _   ||   _   | _____| ||   _   ||     |_ |   _   |  |   |  |     |_ |   _   |
|__| |__||__| |__||_______||__| |__||_______||__| |__|  |___|  |_______||__| |__|

[*] Starting hashcatch setup
[*] Enter your wireless interface: wlan1
[*] Trying to set the given interface to monitor mode
[+] The adapter is working in monitor mode!
./hashcatch: line 88: /etc/hashcatch/hashcatch.conf: No such file or directory
[!] The following packages are missing. Please ensure that you have installed them properly before starting hashcatch
        hashcat-utils
[*] Done

```
i followed almost every tutorial on web and got no solution. finally figured it out from a video : # [cap2hccapx](https://www.youtube.com/watch?v=tOCbcygOvX0).

hashcatch uses cap2hccapx and when this module is not found in your /bin/ folder it fails to see the hashcat utils. there are a lot of solutions for this. this is the one i found useful
```
wget https://raw.githubusercontent.com/hashcat/hashcat-utils/master/src/cap2hccapx.c
gcc cap2hccapx.c -o cap2hccapx
cp cap2hccapx /bin/capcap2hccapx
```
and just like that the problem was solved!!

now if we run the command `./hashcatch --setup` again it might show as below:
```
root@kali:~/hashcatch# ./hashcatch --setup

 __   __  _______  _______  __   __  _______  _______  _______  _______  __   __
|  | |  ||   _   ||       ||  | |  ||       ||   _   ||       ||       ||  | |  |
|  |_|  ||  |_|  ||  _____||  |_|  ||       ||  |_|  ||_     _||       ||  |_|  |
|       ||       || |_____ |       ||       ||       |  |   |  |       ||       |
|       ||       ||_____  ||       ||      _||       |  |   |  |      _||       |
|   _   ||   _   | _____| ||   _   ||     |_ |   _   |  |   |  |     |_ |   _   |
|__| |__||__| |__||_______||__| |__||_______||__| |__|  |___|  |_______||__| |__|

[*] Starting hashcatch setup
[*] Enter your wireless interface: wlan1
[*] Trying to set the given interface to monitor mode
[+] The adapter is working in monitor mode!
./hashcatch: line 88: /etc/hashcatch/hashcatch.conf: No such file or directory
[!] The following packages are missing. Please ensure that you have installed them properly before starting hashcatch
        jq
[*] Done
```
to solve this just install jq: 
```
apt install jq
```

another issue that can arise is this:

```
root@kali:~/hashcatch# ./hashcatch --setup

 __   __  _______  _______  __   __  _______  _______  _______  _______  __   __                                                                                        
|  | |  ||   _   ||       ||  | |  ||       ||   _   ||       ||       ||  | |                                                                                          |
|  |_|  ||  |_|  ||  _____||  |_|  ||       ||  |_|  ||_     _||       ||  |_|                                                                                          |
|       ||       || |_____ |       ||       ||       |  |   |  |       ||                                                                                               |
|       ||       ||_____  ||       ||      _||       |  |   |  |      _||                                                                                               |
|   _   ||   _   | _____| ||   _   ||     |_ |   _   |  |   |  |     |_ |   _                                                                                           |
|__| |__||__| |__||_______||__| |__||_______||__| |__|  |___|  |_______||__| |__                                                                                        |

[*] Starting hashcatch setup
[*] Enter your wireless interface: wlan1
[*] Trying to set the given interface to monitor mode
[+] The adapter is working in monitor mode!
./hashcatch: line 88: /etc/hashcatch/hashcatch.conf: No such file or directory
[*] All necessary packages are found installed
[*] Done
```
this is caused as hashcatch cannot create folders to solve the issue just create all the missing directories (not files)
```
mkdir /etc/hashcatch/
```

now run `./hashcatch --setup` again and all problems should be solved.


**thats it ....**


now you can run `./hashcatch` to capture all nearby handshakes. or use `cp hashcatch /bin/hashcatch` to run the script from anywhere by typing `hashcatch`

usage : [https://asciinema.org/a/AQEzLSxo7teoxPzNSJfwn4UNQ](https://asciinema.org/a/AQEzLSxo7teoxPzNSJfwn4UNQ)

Handshakes captured will be stored in `/usr/share/hashcatch/handshakes/`


The captured WiFi network's BSSID and ESSID will be added to `/usr/share/hashcatch/db`

The configuration file can be found in `/etc/hashcatch/hashcatch.conf`

to cahnge the wifi interface:
use nano 
```
nano /etc/hashcatch/hashcatch.conf
```
and change `interface=wlan1` to the prefered wifi interface.

You can also add an `ignore` field to mention the WiFi networks you want hashcatch to ignore while running

**example**
```
interface=wlan0
ignore=Google Starbucks,AndroidAP
```


[<- cd ..](https://kalipiconf.tk/list)

[<- cd /home/](https://kalipiconf.tk/)
