RTL8192FU driver for Linux kernel 

------------------

Info:  Builtin rtl8192fu support added to Linux kernel 6.5.

https://github.com/torvalds/linux/commit/c98411dc8cf6c15b8dbbfb37475bcc08b8958880

------------------

## How to install

`sudo apt-get install build-essential git dkms linux-headers-$(uname -r)`

`git clone https://github.com/kelebek333/rtl8192fu-dkms`

`cd ./rtl8192fu-dkms`

`sudo dkms install .`


#### Blacklist (alias) for kernel 6.5 and up

If you are using kernel 6.5 and up, you must use a configuration file with following command for preventing to conflict rtl8192fu module with built-in rtl8xxxu module.

`sudo cp ./rtl8192fu-alias-blacklist.conf /etc/modprobe.d/`

##### Then you must update initramfs

For initramfs

`sudo update initramfs -u`

For dracut

`sudo dracut -q --force`


------------------

## How to uninstall

`sudo dkms remove rtl8192fu/5.8.6.2 --all`


------------------

## How to install from PPA repository

You can install rtl8192fu driver with following commands from PPA.

for xUbuntu 16.04-18.04-20.04-21.04-21.10 / Linux Mint 18.x-19.x-20.x

`sudo add-apt-repository ppa:kelebek333/kablosuz`

`sudo apt-get update`

`sudo apt install rtl8192fu-dkms`


You can purge packages with following commands

`sudo apt purge rtl8192fu-dkms`
