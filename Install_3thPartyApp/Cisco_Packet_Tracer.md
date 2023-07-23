# Install step by step
---
## Step 1
Open your web browser on your Ubuntu computer and after viewing the Netacad site, enter your registered user information and log in. Then, click Download Packet Tracer from the Resources drop-down list on the Cisco Networking Academy homepage.
After scrolling down the webpage a little bit, click on the 64 Bit Download link under the Ubuntu Desktop Version 8.2.0 English title and save the CiscoPacketTracer_820_Ubuntu_64bit.deb file to your computer.
## Step 2
To install the Packet Tracer setup file with the deb extension that you downloaded to your computer, first open the terminal by pressing the CTRL + Alt + T keys together, and then go to the location where you downloaded the file.
 ```
sudo apt install ./CiscoPacketTracer_820_Ubuntu_64bit.deb
 ``` 
You can also install the PacketTracer.deb package using the command below.
 ```
sudo apt install ./CiscoPacketTracer_820_Ubuntu_64bit.deb
 ``` 
## Step 3
When you extract the installation file of Packet Tracer and see that the required dependent packages are not installed, first press Y to confirm the necessary packages such as “libgl1-mesa-glx or libxcb-xinerama0-dev” to be downloaded and installed from the Internet by executing the “sudo apt install -f” command in the terminal and then press Enter.
 ``` 
sudo apt install -f
```
## Step 4
executing the packettracer command in the terminal.
 ``` 
packettracer
```
In old versions of Packet Tracer, you had the right to register up to 3 projects without logging in to Cisco. However, in new versions, you now need to log in to your Netacad account.
## Step 5
In this step, when you try to log in to Netacad, the login screen where you enter your account information appears black or white and if you cannot log in, you can fix this problem by temporarily turning off your internet, or you should edit the cisco-pt.desktop file as a permanent solution.

To solve the login problem, open the terminal and execute the command “sudo nano /usr/share/applications/cisco-pt.desktop”. After viewing the contents of the cisco-pt.dektop file, change the Exec value as follows.
 ``` 
Change (Exec=/opt/pt/packettracer %f)
To (Exec=/opt/pt/packettracer --no-sandbox %f)
```
# How to Create a Desktop Shortcut
To copy the shortcut in the applications to the desktop, execute the command “cp /usr/share/applications/cisco-pt.desktop ~/Desktop/” in the terminal.
 ``` 
cp /usr/share/applications/cisco-pt.desktop ~/Desktop/
```
After copying the shortcut, execute the command “chmod +x cisco-pt.desktop” to make the file executable.
 ``` 
chmod +x ~/Desktop/cisco-pt.desktop
```
If the Packet Tracer desktop shortcut is still not active, right-click on it and click Allow Launching. After this process, you will see that the desktop shortcut is active.

# How to Uninstall Packet Tracer
If you want to uninstall the Packet Tracer software from your Ubuntu computer, you can do this with a single line command using the terminal.

 ``` 
sudo apt remove packettracer
```
Execute the command below to delete the Cisco Packet Tracer desktop shortcut as well.
 ``` 
sudo rm -rf ~/Desktop/cisco-pt.desktop
```
Finally, after uninstalling a program in Ubuntu, execute the command below to delete the useless files of the packages received and prevent your system’s cache from growing.
 ``` 
sudo apt autoclean && sudo apt autoremove

```
