# AdGuard PS4 Users Guide

'Users Guide' via the help of <b>AdGuard Home</b>

### How to use?

Step 1: Install AdGuard Home through their official repo (https://github.com/AdguardTeam/AdGuardHome)


Step 2: Go to releases (https://github.com/AdguardTeam/AdGuardHome/releases/tag/v0.107.2) and select the OS of your choice


**Step 2 (Easy Install for Linux): SSH into your device and run - curl -sSL https://raw.githubusercontent.com/AdguardTeam/AdGuardHome/master/scripts/install.sh | sh


And it should do the rest - In order to create a service type in sudo /opt/AdGuardHome/AdGuardHome -s install (This creates a services for you and runs it on every startup)


Step 3: Open your AdGuard setup by visiting the http://IP_OF_YOUR_DEVICE_INSTALLED:3000


Step 4: Once the setup has been completed you will notice that you will get redirected to port 80 instead of 3000 now.


Step 5: Changing the port 80 back to 3000 as we will use this for the 'Users Guide' - SSH or RDP back into your device


Step 6: Now type in /opt/AdGuardHome/AdGuardHome -p 3000 (This will switch the HTTP port from 80 to 3000 which we will be using for the guide) - Do note that the configuration changes for 'Windows'


Step 7: Open your browser and navigate to your http://IP_OF_YOUR_DEVICE_INSTALLED:3000 and it should now display you the AdGuard page instead - As you can see at this point your device has the port 80 free and we can now use it for the 'Users Guide'


Step 8: Now once you are in the AdGuard Home Interface (Port 80 - At this point you are good to go) - Under 'Filters' go to 'Custom filtering rules' and paste in the following values
<p><code> https://github.com/upal212/adguard-ps4-usersguide/blob/main/adguard-psn-block.txt</code></p>
<p>What this does is that it blocks PSN and Updates in order to avoid mistakes in the future</p>


Step 9: Now navigate to 'Filters' once again and click on 'Custom filtering rules'


Step 10: Create DNS rewirtes exactly with the same values as the link 
<p align="center">
<img alt="DNS Rewrites" src="https://raw.githubusercontent.com/upal212/adguard-ps4-usersguide/main/dns-rewrites.PNG"/></p>
Change the IP under 'Answer' with your Device's IP which will run the Web Server on port 80 (I have installed on the same machine in order to avoid in the inconvinience) Do note that: This will redirect to the Any IP address under your network or outside (LAN/WAN).


Step 11: Install Apache according to your distro/OS - I am using Ubuntu so I had followed 'sudo apt install apache2' (If it says cannot find the package run 'sudo apt-get update' on your system)


<b>**For Windows I would recommend installing XAMPP as it is easy to setup</b>


Step 12: Once Apache has been setup and running - you can start it through 'systemctl' for Linux distributions and for 'Windows - XAMPP' can be run through 'apache_start.bat'


Step 13: Navigate to http://IP_OF_YOUR_DEVICE_INSTALLED:80 - It should now display you the 'Apache/XAMPP' page instead.


<b>**Linux users only</b>


*Step 14: SSH back into your device which is running Apache and type in 'cd /var/www/html'


*Step 15: Type in mkdir -p document/gb/ps4


*Step 16: Paste your host file in here with the index.html (Cache is always preferred)


<b>**Windows users only</b>


*Step 14: RDP back into your device running the XAMPP


*Step 15: Navigate to your XAMPP's default installed folder and under 'htdocs' folder create the following folder(s) - first 'document' then under that 'gb' then under 'gb' should be the 'ps4' folder - Basically it should look like 'htdocs/document/gb/ps4'


*Step 16: Paste in your host file in here with the index.html (Cache is always preferred)


Step 17: Now switch over to your PS4 and go under Settings>Network>Set Up Internet Connection>Use WiFi(according to your choice)>Custom>IP Address Settings - Automatic>DHCP Host Name - No Not Specify>DNS Settings - Manual>Primary DNS should be the IP address of your AdGuard Home - Secondary DNS repeat the same thing put the IP address of your AdGuard Home>MTU Settings - Automatic>Proxy Server - Do Not Use


Step 18: Test Internet Connection - you should now have access to the internet but not PSN


Step 19: Open 'Settings>User's Guide' - It should now load up the Apache page with the host file instead of the default PS4 page


Step 20: Have fun!


***Documentation: https://github.com/AdguardTeam/AdGuardHome/wiki/Getting-Started

----------

## Credits

All credits to the [AdGuard Team](https://adguard.com) for their great platform.

Do follow the individual licenses of these files as supplied by the authors.
