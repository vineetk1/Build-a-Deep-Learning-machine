<!-- vim-markdown-toc GFM -->


<!-- vim-markdown-toc -->
# Pick hardware components
Register for an account at <a href="https://pcpartpicker.com" target="_blank">PC Part Picker</a>. This site is invaluable for building a computer. It lists prices of components from various vendors, detects incompatibilities among selected components, keeps track of wattage the components consume, and a lot more.  

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
&emsp; &emsp; &emsp;  &emsp; &thinsp;  USB stick   
$1365 &emsp; &emsp; Total includes rebates, sales tax, and shipping; but excludes Monitor, Keyboard, Mouse, and USB stick  

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
1. Spend sufficient time in developing a strategy to route the cables between the connectors of the Front Panel/Back Panel/Power Supply/Fans and the connectors on the motherboard. Cables should be routed such that the airflow is not obstructed, the status LEDs are visible, the clear CMOS memory jumper pins and all other parts that need to be accessed are accessable, and the cables criss-cross the motherboard as less as possible. Also, develop a checklist of connections. As a side note, my Power Supply has a fan, the CPU has a fan, the GPU has two fans, and there are two fans pre-installed in the Case.
1. Use appropriate cables to connect the connectors of the Front Panel/Back Panel/Power Supply/Fans with those on the motherboard. Go through the checklist, developed earlier, to confirm that all the connections have been made.
# Boot the computer 
1. Create a bootable USB stick for the OS. I will install the Ubuntu OS. As of this writing, Ubuntu Desktop 18.04 is the stable and latest version. This tutorial on <a href="https://tutorials.ubuntu.com/tutorial/tutorial-create-a-usb-stick-on-ubuntu#0" target="_blank">creating a bootable USB stick</a> makes this process very simple.
1. Connect external peripherals to the Computer. Connect the Computer with the Keyboard, Mouse, Display, Bootable USB stick, and optionally the Internet. Note that there are Display ports (e.g. DVI, HTML) that are controlled by the CPU, and a separate set of Display ports of the GPU. Since the GPU is installed, the CPU display ports will not work. Connect an appropriate display port of the GPU with the Display.
1. Connect the Computer Power Supply, Display Power Supply, etc. with the Power Outlet.
1. Enter the BIOS. According to my Motherboard's User Manual, use the DELETE key to enter the BIOS. So, press the DELETE key and Turn ON the Computer. The Computer should enter the BIOS with messages and instructions displayed on the Monitor. Release the DELETE key. 
   * If there is no text on the Monitor, or some other peripheral does not work, then this is an excellent opportunity to learn more about the computer. There is a wealth of information on the web that will help in troubleshooting.
   * If the computer is in the BIOS, set the date and time, verify that the BIOS recognizes the components (e.g. RAM, SSD, GPU, etc) and that it is controlling the fans.  
   * Exit the BIOS, and the computer will enter the bootable USB that has the Ubuntu OS.
1. Install the OS. During Ubuntu installation, answer the questions to customize the installation. If the computer is connected to the Internet, software will be loaded from the Internet.
# Remotely connect with the computer using SSH
From this point forward, this computer is called a Server and a computer that remotely connects to this Server is called a Client.
## &emsp; &emsp; Server side
Install SSH.
```
sudo apt-get install openssh-server
```
Start SSH and check its status.
```
sudo service ssh start
sudo service ssh status
```
Get IP address that will be used later.
```
ifconfig -a
```
## &emsp; &emsp; Client side
Install SSH.
```
sudo apt-get install openssh-client
```
Use this <a href="https://www.digitalocean.com/community/tutorials/how-to-set-up-ssh-keys-on-ubuntu-1804" target="_blank">tutorial</a> to (1) Generate a public/private rsa key pair, and (2) Install the client's public key at the Server.   
Briefly, the following two commands are used.  
1. Generate public/private rsa key pair.
```
ssh-keygen
```
2. Install the client's public key at the Server. The server's IP address can be used for remote_host.
```
ssh-copy-id username@remote_host
```
Remotely log into the Server. The server's IP address can be used for remote_host.
```
ssh username@remote_host
```
The Client is now remotely connected with the Server. 
# Install Nvidia GPU drivers
Check for recommended driver.
```
ubuntu-drivers devices
```
Install the recommended driver.
```
sudo ubuntu-drivers autoinstall
```
Verify driver version, plus other information about the GPU.
```
nvidia-smi
```
# Install Deep Learning software
## &emsp; &emsp; Install CUDA toolkit for Nvidia GPU
Install CUDA 9.1 from Ubuntu 18.04 repository.
```
sudo apt install nvidia-cuda-toolkit
```
Verify installation.
```
nvcc -V
```
## &emsp; &emsp; Install PyTorch, a deep-learning framework

Ubuntu 18.04 comes pre-installed with “python3.6” but not with its package management system “pip”.
Install pip.
```
sudo apt install python3-pip
```
There are many Deep Learning frameworks such as TensorFlow, Keras, and PyTorch. I will install PyTorch from <a href="https://pytorch.org/" target="_blank">HERE</a>. On that webpage, I selected the following options: OS = Linux, Package Manager = pip, Python = 3.6, CUDA = 9.1. The output of the selection were the commands to install PyTorch and Torchvision. I added "sudo -H" to the commands. Torchvision is a software package for computer vision, and its installation is optional. Install PyTorch, and optionally Torchvision.
```
sudo -H pip3 install http://download.pytorch.org/whl/cu91/torch-0.4.0-cp36-cp36m-linux_x86_64.whl 
sudo -H pip3 install torchvision
```
As of this writing, PyTorch 0.4.0 is the latest version.  
Verify that PyTorch detects CUDA by running the following commands in the Python interpreter.
 ```
>>> import torch
>>> torch.cuda.is_available()
True
 ```
The status "True" means that PyTorch is using the GPU.
