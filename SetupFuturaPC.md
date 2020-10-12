# Set up a PC to run the Singer Futura 150 CE

## Device

[Singer Futura 150 CE](http://futura-support.com/products/ce-150) specifications

## PC

Laptop running Windows 10 with [Oracle Virtual Box](https://www.virtualbox.org/)

**TODO:  Add version**

## Software

- Virtual Box [Download](https://download.virtualbox.org/virtualbox/6.1.14/VirtualBox-6.1.14-140239-Win.exe)
- Singer Futura Setup CD - Not available online.  Had to purchase on [eBay](https://www.ebay.com/).  
- Ubuntu OS [Download](https://ubuntu.com/download/desktop)

## Virtual box install

Follow the directions on line

## Ubuntu installation

- Create a new virtual machine instance
- make sure the machine has sufficient processor, memory, and video memory
- insert the Ubuntu `.iso`
- Start the VM and follow the Ubuntu installation directions.  Choose a normal setup
- After restarting at the end of the installation process, allow Ubuntu to conduct system updates.
- Start a terminal

```bash
sudo apt update
sudo apt-get upgrade
sudo apt-get install gcc make perl
```

- Insert the Virtual Box guest additions CD.  The installation should start, follow the prompts.  **TODO:  how to start**
- Shut down the VM
- change settings to add a shared file location with the futura CD
- start the VM
- mount the shared location
- copy futura software to the VM

## Wine installation

- open a terminal
- wine-hq link
- add directions
- mono and gecko need to be installed
- install winetricks
- export WINEARCH=win32
- winetricks mcf42
- cd <location of futura startup CD>
- wine FuturaStart.exe
- follow start up prompts.  Don't change windows filepaths or settings

## Connect and start-up

- connect the Futura via USB
- send the USB signal through to the VM
- navigate to the Futura diectory /home/rcc/.wine/dos.....
- wine Futura.exe



