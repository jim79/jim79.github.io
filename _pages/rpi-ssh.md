---
title: Configure ssh on Raspberry Pi 
permalink: /rpi-ssh-configure/
layout: single
---
## Configure SSH on Raspberry Pi
The rpi-imager allows one to enable SSH from GUI while flashing the OS on to SD card. But you can also ssh on Raspberry Pi in headless mode (ie, without a monitor) in case you forgot to enable ssh while flashing the OS.

#### Create the ssh file
- Create a blank file on your PC/Laptop
- Name it ssh (without any extension)
- Copy and paste it in boot folder of sd card
- When the Raspberry Pi boots, it looks for the ssh file
- If it is found, SSH is enabled and the file is deleted
- The content of the file does not matter; it could contain text, or nothing at all

#### Create the default user
- Create a file called userconf or userconf.txt in the boot partition of the SD card
- This file should contain a single line of text consisting of username:encrypted- password \
format  ```<desired username>:encrypted- password```
For instance if your desired user name is pi, the line of text would be ```pi:<encrypted- password>```

#### Creating the encrypted password for the default user created above
- You can create the encrypted password using openssl
- For instance to encrypt your password ‘raspberry’,  enter in the terminal
```echo raspberry | openssl passwd  -6  -stdin```
- And we get the encrypted password something like this
```$6$JyfCNXDuUtIPcKzl$4XogJWqxHhYOqhL9AbebdZwx95jfcVlkSgaCnkEdib.o.qHZ4qT.abPMJ8oFKZ8a0Jd/YpKw3WDqwl8Muwcac1``` 
- Copy and paste the encrypted password after the colon (:) in the userconf file as shown below
```pi:$6$JyfCNXDuUtIPcKzl$4XogJWqxHhYOqhL9AbebdZwx95jfcVlkSgaCnkEdib.o.qHZ4qT.abPMJ8oFKZ8a0Jd/YpKw3WDqwl8Muwcac1```
- Save the ```userconf.txt``` file into the boot partition of the SD card