# Set up a PC to run the Singer Futura 150 CE

## Device

[Singer Futura 150 CE](http://futura-support.com/products/ce-150) specifications

## PC

Laptop running Windows 10 with [Oracle Virtual Box](https://www.virtualbox.org/) 6.1

## Software

- Virtual Box [Download](https://download.virtualbox.org/virtualbox/6.1.14/VirtualBox-6.1.14-140239-Win.exe)
- Singer Futura Setup CD - Not available online.  Had to purchase on [eBay](https://www.ebay.com/).  
- Ubuntu OS [Download](https://ubuntu.com/download/desktop)

## Virtual box install

Follow the [directions](https://www.virtualbox.org/manual/ch02.html) online

## Ubuntu installation

- Create a new virtual machine instance
- Make sure the machine has sufficient processor, memory, and video memory (without sufficient video memory, the display hangs after logon)
- insert the Ubuntu `.iso`
- Start the VM and follow the Ubuntu installation directions.  Choose a normal setup
- After restarting at the end of the installation process, allow Ubuntu to conduct system updates.
- Start a terminal

```bash
sudo apt update
sudo apt-get upgrade
sudo apt-get install gcc make perl
sudo apt update
sudo apt install -y build-essential linux-headers-$(uname -r)
```

- Insert the Virtual Box guest additions CD.  The installation should start, follow the prompts.  **TODO:  how to start**
- Shut down the VM
- change settings to add a shared file location with the futura CD
- start the VM
- mount the shared location

```bash
sudo mount -t vboxsf <HostShareName> <GuestMountLocation>
```

- copy futura software to the VM

## Wine installation

See directions [here](https://wiki.winehq.org/Ubuntu) and [here](https://askubuntu.com/questions/169218/winetricks-cant-install-mfc42).

- open a terminal

```bash
sudo dpkg --add-architecture i386 
wget -nc https://dl.winehq.org/wine-builds/winehq.key
sudo apt-key add winehq.key
sudo add-apt-repository 'deb https://dl.winehq.org/wine-builds/ubuntu/ focal main'
sudo apt update
sudo apt install --install-recommends winehq-stable
sudo apt-get install winetricks
export WINEARCH=win32
winetricks mfc42
```

## Setup the Futura software

- cd <location of futura startup CD>

```bash
wine FuturaStart.exe
```

- During installation, wine will ask to install `mono` and `Gecko`.  Click yes for both.
- follow start up prompts.  Don't change windows filepaths or settings

## Connect and start-up

- connect the Futura via USB
- send the USB signal through to the VM
- navigate to the Futura diectory /home/rcc/.wine/dos.....
- wine Futura.exe

