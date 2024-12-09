---
title: Configure wifi on Raspberry Pi 
permalink: /rpi-wifi-configure/
layout: single
---

## Configure wifi by editing the ```wpa_supplicant.conf``` file
1. Load the SD card containing the OS on a Laptop/PC
2. Open the wpa_supplicant.conf file in a text editor We shall use ```nano``` text editor.
3. ```sudo nano rootfs/etc/wpa_supplicant/wpa_supplicant.conf```

A typical ```wpa_supplicant.conf``` file looks like this

```
ctrl_interface=DIR=/var/run/wpa_supplicant GROUP=netdev
country=<IN
update_config=1

network={
 ssid="rpi_lab"
 psk="12345"
}

```
#### Add the entries of the new wifi connection so that the modfied file is as below

```
ctrl_interface=DIR=/var/run/wpa_supplicant GROUP=netdev
country=<IN
update_config=1

network={
 ssid="rpi_lab"
 psk="12345"
}

network={
ssid="EC204"
psk="cet@123"
}

```
#### Press ```ctrl + s``` to save the file
#### Press ```ctrl + x``` to exit the editor
#### Load the SD card into Raspberry Pi and power up

## Configure wifi headless
The rpi-imager allows one to configure the wifi from GUI while flashing the OS on to SD card. But sometimes you may have configure the wifi on Raspberry Pi in headless mode (ie, without a monitor). This is done by creating a ```wpa_supplicant.conf``` file in the boot folder of SD card. You can also create a default user with password as explained in this post below. A template ```wpa_supplicant.conf``` is also provided.
### <a href="https://jim79.github.io/assets/configure_wifi_raspberrypi_headless.pdf">Configure wifi on Raspberry Pi headless</a>


### <a href="https://jim79.github.io/assets/wpa_supplicant.conf">A template wpa_supplicant.conf file</a>


