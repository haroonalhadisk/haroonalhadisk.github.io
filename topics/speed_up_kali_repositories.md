# Speed up kali repositories

On an average kali linux repostories left by default are too slow. This means that when updating (apt update) or upgrade (apt upgrade), installing an app etc the download speed of the pi is too low. Approx. 45-60kb/s. this can take too long even for a small update. We can fix the issue using alternative mirrors that are much faster. Doing this manually is a tedious task. So we use a script to automate the process by checking for the fastest server and updating the repository file. 

**works on any kali distribution**

lnk to [**original post**](https://www.metahackers.pro/speed-kali-linux-update/). *visit here if you want to update manually.*

first we clone the repository
```
git clone https://github.com/IceM4nn/mirrorscript-v2.git
```
It is best to do this in the root directory. Now we need to move to the *mirrorscript-V2* folder.
```
cd mirrorscript-v2
```
run the python file *mirrorscript-v2.py* with the following arguments.
```
python3 mirrorscript-v2.py -https -v
```
***-https*** is for getting only the https mirrors and ***-v*** is for verbose output. Type in `python3 mirrorscript-v2.py -h` to get a list of all arguments.

## hints
if you get the below error when running the script it is because requests package is missing
```
root@kali-pi:~/mirrorscript-v2# python3 mirrorscript-v2.py -h
Traceback (most recent call last):
  File "mirrorscript-v2.py", line 3, in <module>
    import subprocess, requests, re, sys
ModuleNotFoundError: No module named 'requests'
```
to install requsts package make sure your python is updated to the latest version and do apip install
```
apt install python3
apt install python3-pip
pip3 install requests
```
and this should solce the issue

out put afterards:
```
root@kali-pi:~/mirrorscript-v2# python3 mirrorscript-v2.py -https -v
#
# Mirrorscripts-v2 - By Hazmirul Afiq
# Automatically select the best Kali mirror and apply the configuration
# https://github.com/IceM4nn/mirrorscript-v2
# https://www.metahackers.pro/speed-kali-linux-update/
#

[-] Checking if 'apt-transport-https' package is installed.
        ! apt-transport-https is NOT installed. Attempting to install ...
        - Installing apt-transport-https

Selecting previously unselected package apt-transport-https.
(Reading database ... 207072 files and directories currently installed.)
Preparing to unpack .../apt-transport-https_1.7.0~rc2_all.deb ...
Unpacking apt-transport-https (1.7.0~rc2) ...
Setting up apt-transport-https (1.7.0~rc2) ...

        - apt-transport-https installed succesfully
[+] Getting mirror list ...
[+] Found a lists of mirrors:
        - https://mirror.karneval.cz/pub/linux/kali
        - https://ftp.acc.umu.se/mirror/kali.org/kali
        - https://mirrors.dotsrc.org/kali
        - https://ftp.halifax.rwth-aachen.de/kali
        - https://ftp2.nluug.nl/os/Linux/distr/kali
        - https://ftp1.nluug.nl/os/Linux/distr/kali
        - https://mirror.neostrada.nl/kali
        - https://archive-4.kali.org/kali
        - https://hlzmel.fsmg.org.nz/kali
        - https://wlglam.fsmg.org.nz/kali
        - https://kali.download/kali
        - https://mirrors.ocf.berkeley.edu/kali

[+] Checking mirrors ...
[+] Finding the best latency
        - kali.download                  : 34.752
        - mirrors.dotsrc.org             : 282.258
        - ftp1.nluug.nl                  : 167.900
        - mirror.neostrada.nl            : 192.818
        - ftp2.nluug.nl                  : 165.252
        - archive-4.kali.org             : 182.549
        - ftp.acc.umu.se                 : 293.370
        - mirrors.ocf.berkeley.edu       : 253.168
        - mirror.karneval.cz             : 278.571
        - ftp.halifax.rwth-aachen.de     : 204.725
        - wlglam.fsmg.org.nz             : 411.268
        - hlzmel.fsmg.org.nz             : 407.401

[+] Fastest mirror: ('kali.download', '034.752')
[+] Preparing ...
        - Making a backup file /etc/apt/sources.list.bk ...
        - Checking sources.list for older entries ...
        - Commenting older entries ...
        - Done

[+] Updating sources.list with new entry ...
        - Your new mirror: https://kali.download/kali

[+] Done!
        - Run 'apt clean; apt update' for the changes to load.
```


we can now delete the *mirrorscript-V2* if needed. just `cd ..` and then use command `rm -r mirrorscript-V2`

[<- cd ..](https://kalipiconf.tk/list)

[<- cd /home/](https://kalipiconf.tk/)
