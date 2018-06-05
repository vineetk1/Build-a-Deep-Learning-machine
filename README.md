**NOTE: This is work in progress. This message will be removed soon when this work is completed.**   
<!-- vim-markdown-toc GFM -->


<!-- vim-markdown-toc -->
# Pick hardware components
Register for an account at <a href="https://pcpartpicker.com" target="_blank">PC Part Picker</a>. This site is invaluable for building a computer. It lists prices of components from various vendors, detects incompatibilities among selected components, keeps track of wattage the components will consume, and a lot more.  

Following is my list of components and their prices:   
$ &thinsp; 250 &emsp; &emsp; i5-8400 CPU and Motherboard   
$ &thinsp; 525 &emsp; &emsp; GeForce GTX 1080 8GB GPU   
$ &thinsp; 294 &emsp; &emsp; 32GB (2 x 16GB) DDR4-2400 RAM   
$ &thinsp; 200 &emsp; &emsp; 500GB NVMe PCIe M.2 2280 SSD   
$ &ensp; 56 &emsp; &emsp; Fully-Modular ATX Power Supply   
$ &ensp; 40 &emsp; &emsp; ATX Mid Tower Case   
&emsp; &emsp; &emsp;  &emsp; &thinsp;  Monitor   
&emsp; &emsp; &emsp;  &emsp; &thinsp;  Keyboard   
&emsp; &emsp; &emsp;  &emsp; &thinsp;  Mouse   
&emsp; &emsp; &emsp;  &emsp; &thinsp;  USB drive   
$1365 &emsp; &emsp; Total including rebates, sales tax, and shipping; but excluding Monitor, Keyboard, and Mouse  

I already have a cheap monitor, a USB drive, and a wired USB keyboard and mouse that I will use to boot this computer and install the Secure Shell (SSH). Thereafter, I should have no need for these accessories (i.e. monitor, keyboard, mouse, USB) because I will use my laptop to log into this computer via my home network (and also the Internet) using SSH.   
My specific components list is <a href="https://pcpartpicker.com/user/vink9482/saved/M6WxYJ" target="_blank">HERE</a>. Add a hard drive if 500 GB of SSD capacity is insufficient.
# Assemble hardware components
Spend sufficient time in understanding the instructions in the installation manuals and the videos that come with the components. Carefully follow directions in the installation manuals and the videos to install the components. I installed the components in the following order:   
1. Install the CPU in the Motherboard.
1. Install the Fan on the CPU. The i5-8400 CPU comes with a Fan.
1. Install the RAM in the Motherboard.
1. Install the Motherboard in the Case. 
1. Install the SSD in the Motherboard.
1. Install the GPU in the Motherboard.
1. Install the Power Supply in the Case.
1. Spend sufficient time in developing a strategy to route the cables between the connectors of the Front Panel/Back Panel/Power Supply/Fans and the connectors in the motherboard. Cables should be routed such that the airflow is not obstructed, the status LEDs are visible, the clear CMOS memory jumper pins and all other parts that need to be accessed are accessable, and the cables criss-cross the motherboard as less as possible. Also, develop a checklist of connections. As a side note, my Power Supply has a fan, and there are two fans pre-installed in the Case. Along with the CPU fan, my computer has four fans.
1. Use appropriate cables to connect the connectors of the Front Panel/Back Panel/Power Supply/Fans with those in the motherboard. Go through the checklist, developed earlier, to confirm that all the connections have been made.
# Boot the computer 
1. Create a bootable USB stick for the OS. I will install the Ubuntu OS. As of this writing, Ubuntu Desktop 18.04 is the stable and latest version. This tutorial on <a href="https://tutorials.ubuntu.com/tutorial/tutorial-create-a-usb-stick-on-ubuntu#0" target="_blank">creating a bootable USB stick</a> makes this process very simple.
1. Connect external peripherals to the Computer. Connect the Computer with the Keyboard, Mouse, Display, Bootable USB stick, and optionally the Internet. Note that there are Display ports (e.g. DVI, HTML) that are controlled by the CPU, and a separate set of Display ports of the GPU. Since the GPU is installed, the CPU display ports will not work. Connect an appropriate display port of the GPU with the Display.
1. Connect the Computer Power Supply, Display Power Supply, etc. with the Power Outlet.
1. Enter the BIOS. According to my Motherboard's User Manual, use the <DELETE> key to enter the BIOS. So, press the <DELETE> key and Turn ON the Computer. The Computer should enter the BIOS with messages and instructions displayed on the Monitor. Release the <DELETE> key. 
   * If there is no text on the Monitor, or some other peripheral does not work, then this is an excellent opportunity to learn more about the computer. There is a wealth of information on the web that will help in troubleshooting.
   * If the computer is in the BIOS, set the date and time, verify that the BIOS recognizes the components (e.g. RAM, SSD, GPU, etc) and that it is controlling the fans.  
   * Exit the BIOS, and the computer will enter the bootable USB that has the Ubuntu OS.
1. Install the OS. During Ubuntu installation, answer the questions to customize the installation. If the computer is connected to the Internet, software will be loaded from the Internet.
# Install other software
## &emsp; &emsp; Install SSH
## &emsp; &emsp; Install Deep Learning software


 
