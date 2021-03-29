# FarmSoftwareProject00
An open source farm software project being worked on by UKUAT members.

## Home Assistant (HASS)
### Instalation
HASS is usually installed on a device such as a RPi, or on a virtual machine such as in a server. Details of how to do this, for both options:
https://www.home-assistant.io/installation/

## ESP Home
To easily develop code for ESP8266/32 microcontrollers, ESP Home can be installed as an add-on to HASS. 

### Nodes
New ESP device that will have code uploaded to it is known as a node. These nodes are accessed at the ESPHome main page. 

![img1](https://user-images.githubusercontent.com/52703479/112815804-99752a80-9078-11eb-8f2d-9df500b0e6d9.png)

Each node has a YAML file assosciated with it. This YAML file can be edited in the web-page GUI, where code segments can added to integrate sensors, switches etc to an ESP device. 

### Finding components/devices/sensors
ESP Home has an in-app GUI that takes you through the process of creating a YAML file to upload to the ESP. This YAML file contains a list of sensors/controls the ESP is connected to. ESP Home has a large built up list of accepted sensors/devices (such as a swicth) that are integrated, and so are easily coded into the YAML file.

![img5](https://user-images.githubusercontent.com/52703479/112815562-5c109d00-9078-11eb-9ef3-9220d9d156bb.png)

It is simply a case of copying the code from ESP Home website, adding to a YAML file, choosing the correct GPIO pin to connect the device to A list of integreated devices is shown here;
https://esphome.io/index.html

For example, code for BMP280:
![img6](https://user-images.githubusercontent.com/52703479/112816729-9a5a8c00-9079-11eb-8490-f0d45328b341.png)



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

![img4](https://user-images.githubusercontent.com/52703479/112816124-f8d33a80-9078-11eb-8a42-d6451294b8a9.png)


If successful, the ESP device will connect with your Home Assistant instance when it is powered up. You can check the logs of the outputs using the ESP Home GUI. 


**Once tyhe first code is uploaded**, the ESP device will then be available for OTA updates if it is connected to the WiFi network. For this, open the node YAML file in the web-page GUI, edit the code, then press upload. The node log will then pop up, showing the progress of the OTA update. 

![img3](https://user-images.githubusercontent.com/52703479/112816364-3a63e580-9079-11eb-86bc-6dac3c99f2aa.png)





