
# User Information

User: ugv_base_station
Password: ospreysystems

# Network Configuration

As configured, the base station computer has a static IP address configured on its Ethernet port. This IP address is conducive to the default subnet of the UGV - 192.168.1.77.



# Installed Applications

##### UGV Joystick

This is a desktop launcher to run the ugv joystick teleoperation launch file. This will open up a terminal application which will display the battery state, and the state of lights and aux power. A camera viewer for the UGV's camera will also open. A connected joypad such as the included Xbox series S/X controller can be used to teloperate the UGV

##### UGV Keyboard

This is a desktop launcher to run the ugv keyboard teleoperation launch file. This will open up a terminal application and an camera viewer for the UGV's camera. The terminal application will display the status of the battery, aux power and lights. You can use the terminal application to control the UGV via keyboard input.
##### Filezilla

This is a file transfer application which can be used to transfer files to other computers, such as the UGV computer itself or the payload computer. Use of this application is beyond the scope of this document. The user is referred to https://wiki.filezilla-project.org/Using

##### Terminator

Terminator is a Linux terminal program. The advantage of terminator vs the stock terminal program that you can split the window horizontally or vertically, as many times as required. To do this right click in the terminal window and click "Split Vertically" etc

##### VS Code

VS Code is the chosen code editor for Osprey Systems Engineering, it is included on the base station computer for the user’s convenience.

##### Vokoscreen

Vokoscreen is a Linux screen capture application.

##### VLC

VLC is a video player application, that can also stream the video from the MK-12 Smart PoE Powerbanks. It is included on the base station computer for the user’s convenience.

##### NMAP

NMAP is a network scanning, terminal application. It is handy for determining the IP addresses of connected devices on the base station computer’s LAN. To use NMAP, first identify your IP address subnet. This can be done using a terminal / terminator. Enter the following command:

$ ip addr show

Ethernet networks will be under eth0, and WiFi will be under wlan0. E.g 192.168.1.77 is the default Ethernet IP address of the base station computer.

Then to scan this LAN, enter the following:

$ nmap 192.168.1.*
##### Anydesk

Anydesk is a Remote Desktop application. This is handy if you want to deploy the UGV on site with a Rajant LAN, and then access it off site. You can remote into the base station computer and take control of the UGV by using the keyboard teleperation application above. 

Use of Anydesk is strictly for private use, and is installed for the user’s convenience. To use Anydesk for commercial applications, you must pay for a license. 

##### OpenSSH-server

OpenSSH-server is a background SSH application that allows other computers on the LAN to SSH into the base station computer (if they have the correct credentials). IT is included here for the user’s convenience.



# Starting Teleoperation Session

If using the Xbox series X/S controller, ensure it is powered on and paired with the base station computer. The controller that is provided with the base station computer has been updated to the latest firmware at the time of delivery and is already paired with the base station computer. Turn it on my pressing the XBOX symbol. It will vibrate when it is connected.

Ensure the UGV is powered on, and connected to the base station computer either through Rajant or WiFi.

Double click on the desktop icon for either ugv joystick, or ugv keyboard, depending on what you want to use. 

##### Control layout

If using the XBOX controller, the control layout is as follows:

LB - dead man, press and hold to drive the UGV around
Left stick - control input for driving the UGV
B - switch on lights
X - switch off lights
Y - switch on aux power
A - switch off aux power

Key bindings for the keyboard teleoperation program are displayed in the terminal window to the user. These will be re-displayed periodically.

##### RVIZ

RVIZ is a ROS visualisation application, that can visualise both 2D and 3D data. Depending on your application and installed software, this can be useful. The use of RVIZ is beyond the scope of this document, however the user can save RVIZ profiles so that they do not have to re enter parameters every time they use the application. To open a profile, click on the top left “open” and navigate to the .rviz file. 

Note that .rviz files should be saved in the default location.

To open RVIZ, once connected to the UGV through either Rajant or WIFI, enter the following in terminator / terminal:

$ rosrun rviz rviz

# UGV Safe Power Down

In order to safely power off the UGV, it is recommended to SSH into it and run the shutdown command. 

$ ssh ubuntu@192.168.1.150
pwd - ospreysystems
$ sudo shutdown now

The same is also true of the payload computer if it is mounted to the UGV.

$ ssh pi5@192.168.1.147
PWD - ospreysystems
$ sudo shutdown now

The payload computer (and any other payloads can then be powered off using the Keyboard shortcut if using the keyboard teleoperation program or the A button on the XBOX controller. 

