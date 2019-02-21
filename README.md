# Pre-installed-ROS-Raspbian-OS-
Raspbian OS with pre-installed ROS environment will be installed on Raspberry Pi 3. Though it will be just the Raspbian Stretch Lite, so configuring it for the internet connectivity and the installation of Desktop i.e. startx is also explained. 
## Flashing SD Card with OS
I have used BalenEtcher named software to flash the OS image to the SD Card. 
You can download the same from the following link: https://www.balena.io/etcher/
To download the image of the OS refer to the following link: https://goo.gl/forms/d1Qa97xm8NhkLTR52
### Steps Flashing the Image onto SD Card
  1. Open BalenaEtcher.
  2. Select the OS image.
  3. Select the SD Card.
  4. Flash it 
### Usernamre and Password
 The default username and Password are given below:
  Username: pi
  Password: rosbots!

Make sure that you expand the memory and change the keyboard type by running the following command 

    raspi-config
## Internet Connectivity for Raspberry Pi
Though you can direclty connect your Pi to internet using Ethernet, bu tin case you don't have an ethernet cable your can use your Mobile Phone using USB tethering to get Pi connected to internet.
#### Steps:
  1.Boot Raspberry Pi

  2.In the start up screen enter the following command to open the file “interfaces”

    > sudo nano /etc/network/interfaces

  sudo will execute the command with administrator privileges

  This will open the file “interfaces” in the location /etc/network

  3.Add the following line “iface usb0 inet dhcp”  below
     
      auto eth0
      iface eth0 inet dhcp

   The modified code will look like

      auto usb0
      iface usb0 inet dhcp
      iface usb0 inet dhcp

  4.To save the file press the following keys
                      ESC
                        :wq 
                        ENTER

  5.Now enter the following command and press ENTER key
                        
      >sudo ifup usb0
   Now you will see some auto generated commands on the screen
      ifup command will bring a network interface up

  6.Reboot Raspberry Pi by executing the command
    
      >sudo reboot
      
 ## Setting up Desktop 
 Now once you are connected to the internet, run 
 
    sudo apt-get update
    sudo apt-get --no-install-recommends 
    sudo apt-get install xserver-xorg 
    sudo apt-get install lxde lxde-core lxterminal lxappearance
    sudo apt-get install lightdm
    sudo apt-get install xinit
##It's Done 
Now just launch the desktop using the following command 
    
    startx
