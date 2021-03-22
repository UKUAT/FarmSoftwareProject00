# FarmSoftwareProject00
An open source farm software project being worked on by UKUAT members.

## Home Assistant (HASS)
### Instalation
HASS is usually installed on a device such as a RPi, or on a virtual machine such as in a server. Details of how to do this, for both options:
https://www.home-assistant.io/installation/

## ESP Home
To easily develop code for ESP8266/32 microcontrollers, ESP Home can be installed as an add-on to HASS. 

### Finding components/devices/sensors
ESP Home has an in-app GUI that takes you through the process of creating a YAML file to upload to the ESP. This YAML file contains a list of sensors/controls the ESP is connected to. ESP Home has a large built up list of accepted sensors/devices (such as a swicth) that are integrated, and so are easily coded into the YAML file.

It is simply a case of copying the code from ESP Home website, adding to a YAML file, choosing the correct GPIO pin to connect the device to A list of integreated devices is shown here;
https://esphome.io/index.html

### Uploading Code
Uploading code to an ESP device is done in two ways;

If it is the first time uploading code, it will need to be manually flashed using a connection to the computer. Firsty, compile the code at ESP Home GUI. If all is fine, it will save and you can download it as a binary file. 
Then, you need to flash this binary file to the ESP device using ESP Home Flasher using Python 
```
pip install esphomeflasher
```
https://github.com/esphome/ESPHome-Flasher

Open this software using cmd `esphomeflasher`
Then select the ESP device on a COM port, and flash with the downloaded binary file. 

If successful, the ESP device will connect with your Home Assistant instance when it is powered up. You can check the logs of the outputs using the ESP Home GUI. 




