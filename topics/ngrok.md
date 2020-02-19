# ngrok.

Tunnels. tunnels. tunnels
 If you have ever tried phishing you will defenetely know what ngrok is. if you don't **you need to**.
 
ngrok is a tunneling tool. What this means in simpler terms is that ngrok can convert your localhost into a remotly accessible ip. It can be http, https, or even tcp.

**why is this so important?**
as you can see if we want to remotely access a device (meterpreter or otherwise) we need to host our device to the web. this is a hard process to do and we need a dedicated router for the same. ngrok makes this much easier. its provides us an internet address along with port number making it possible to hack any device or webpage from our device. visit their [official site](https://ngrok.com/) for more info

## here is how to install ngrok:

first signup to ngrok from here : [signup](https://dashboard.ngrok.com/signup)

Download the zip file using the below command: 
```
wget https://bin.equinox.io/c/4VmDzA7iaHb/ngrok-stable-linux-arm.zip
```
*this link is for linux-arm device if you are downloading for any other device other than the raspberry pi check accordingly and download from [here](https://ngrok.com/download)*

now we need to unzip the file:
```
unzip /path/to/ngrok.zip
```
replace `/path/to/ngrok.zip` with `ngrok-stable-linux-arm.zip` in our case.

now we need to move the ngrok file to /usr/bin/ to be able to use it anywhere in kali.
```
mv ngrok /usr/bin/ngrok
```
now authenticate ngrok with your authtoken. You can get it form [here](https://dashboard.ngrok.com/auth)
```
ngrok authtoken <paste your authtoken here>
```
replace `<paste your authtoken here>` with your authtoken.

**thats it.**
to run ngrok as an http server type in
```
ngrok http 4444
```
where 4444 is the port number *(needs to be same as the port number set while setting up the phshing page or tcp)*.


[<- cd ..](https://kalipiconf.tk/list)

[<- cd /home/](https://kalipiconf.tk/)
