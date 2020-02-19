# Speed up kali repositories

On an average kali linux repostories left by default are too slow. This means that when updating (apt update) or upgrade (apt upgrade), installing an app etc the download speed of the pi is too low. Approx. 45-60kb/s. this can take too long even for a small update. We can fix the issue using alternative mirrors that are much faster. Doing this manually is a tedious task. So we use a script to automate the process by checking for the fastest server and updating the repository file. 

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

we can now delete the *mirrorscript-V2* if needed. just `cd ..` and then use command `rm -r mirrorscript-V2`
