


	      ___           ___                                                   ___     
	     /  /\         /__/\        ___                                      /  /\    
	    /  /:/         \  \:\      /  /\                                    /  /::\   
	   /  /:/           \__\:\    /  /:/      ___     ___   ___     ___    /  /:/\:\  
	  /  /:/  ___   ___ /  /::\  /__/::\     /__/\   /  /\ /__/\   /  /\  /  /:/~/::\ 
	 /__/:/  /  /\ /__/\  /:/\:\ \__\/\:\__  \  \:\ /  /:/ \  \:\ /  /:/ /__/:/ /:/\:\
	 \  \:\ /  /:/ \  \:\/:/__\/    \  \:\/\  \  \:\  /:/   \  \:\  /:/  \  \:\/:/__\/
	  \  \:\  /:/   \  \::/          \__\::/   \  \:\/:/     \  \:\/:/    \  \::/     
	   \  \:\/:/     \  \:\          /__/:/     \  \::/       \  \::/      \  \:\     
	    \  \::/       \  \:\         \__\/       \__\/         \__\/        \  \:\    
	     \__\/         \__\/                                                 \__\/    

list of all topics : [link](https://kalipiconf.tk/list)

# AFTER FRESH INSTALL OF KALI ON PI

## $step 1 :  ./ speedup the repositories  [-h](https://kalipiconf.tk/topics/speed_up_kali_repositories)

		1. git clone https://github.com/IceM4nn/mirrorscript-v2.git
		2. cd mirrorscript-v2
		3. python3 mirrorscript-v2.py -https -v		

## $step 2 : update and upgrade

		1. apt update
		2. apt upgrade
		

## step 3 : install kalipi-config

		1. apt install whiptail parted lua5.1 alsa-utils psmisc libraspberrypi0 libraspberrypi-dev libraspberrypi-doc libraspberrypi-bin
		2. wget -O /usr/local/bin/kalipi-config https://raw.githubusercontent.com/Re4son/RPi-Tweaks/master/kalipi-config/kalipi-config
		3. chmod 755 /usr/local/bin/kalipi-config
		

## step 4 :install wifite

		1. git clone https://github.com/derv82/wifite2.git
		2. cd wifite2
		3. python setup.py install
		4. apt install reaver
		5. apt install bully
		6. apt install pyrit
		7. apt install macchanger
		8. apt install hcxdumptool
		9. INSTALL HASHCAT : 
			i. 	 git clone https://github.com/hashcat/hashcat.git
			ii.  cd hashcat
			iii. make 
			iv.	 make install
		10. INSTALL HCXCAPTOOLS (HCXTOOLS) :
			i. 	 git clone https://github.com/ZerBea/hcxtools
			ii.  apt install libssl-dev
			iii. apt install libcurl4-gnutls-dev
			iv. cd hcxtools/
			v.	 make
			vi.	 make install
			

## step 5 : install fruitywifi

		> You need a Raspbian, Pwnpi or Kali Linux version to use this script.
		> Download the zip file from https://github.com/xtr4nge/FruityWifi/archive/master.zip
		> Unzip the file and run install-FruityWiFi.sh (This script will install all the dependencies and setups)
		> Done.
		> Go to http://localhost:8000 (for http)
		> Go to https://localhost:8443 (for https)

			user: admin
			pass: admin

## step 6 : install ngrok

		1. wget https://bin.equinox.io/c/4VmDzA7iaHb/ngrok-stable-linux-arm.zip
		2. unzip /path/to/ngrok.zip
		3. mv ngrok /usr/bin
		4. ngrok authtoken <paste your authtoken here>

get the auth token from [here](https://ngrok.com/download)	
now to use ngrok you can type `ngrok 4444 http` or `ngrok 1234 tcp`

## step 7 : HiddenEye phishing pages

		1. git clone https://github.com/DarkSecDevelopers/HiddenEye.git
		2. chmod 777 HiddenEye
		3. pip3 install -r requirements.txt
		4. pip3 install requests
		5. python3 HiddenEye.py
	

# Other tips:



## If a grey screen is encountered on vnc 
change /root/.vnc/xstartup contents to this:

	#!/bin/sh
	unset SESSION_MANAGER
	unset DBUS_SESSION_BUS_ADDRESS
	startxfce4 &

	[ -x /etc/vnc/xstartup ] && exec /etc/vnc/xstartup
	[ -r $HOME/.Xresources ] && xrdb $HOME/.Xresources
	xsetroot -solid grey
	vncconfig -iconic &

************************************************************************************************		

## When opening a website shows certificate error or if the time is not correctly configured :

	/etc/init.d/ntp stop
	ntpd -q -g
	/etc/init.d/ntp start

or we can create an executable file that can be run if date issue exists

	nano fixtime
	enter the above commands into the file
	mv fixtime to /usr/bin/fixtime

now you can enter ***fixtime*** as a command and it will fix the issue each time. 

************************************************************************************************

## Auto completion does not work properly

	apt install bash-completion
		
this will bring auto completion everywehere.

## *Screen* is cool tool

watch this video tutorial for better understanding : [How to use GNU SCREEN](https://www.youtube.com/watch?v=I4xVn6Io5Nw)
			
			screen -S [session_name]
			screen -ls					#lists the current sessions
			screen -r [session_name] 	#reattatch to the selected session_name
			within session Ctrl+a 
				then press d to detatch
				k to kill window
				c to create a new window
				n or p to cycle through windows
				\ to kill all windows
				| or S to split screen (press Ctrl+a and tab to switch)
				0,1,2,.... to jump to that window
				w to list all windows
				" to list and select windows
				? help

## Locate command not working
just type in the below command and wait for it to update the database

	updatedb
	
Use this each time a new file is added or when using the locate command.
