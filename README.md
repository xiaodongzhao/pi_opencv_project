# Tutorial to use OpenCV and YOLO on Raspberry Pi

## Requirements

- Raspberry Pi Model B
- Python 3
- Numpy
- OpenCV >= 3.4.2
- Matplotlib
- Jupyter notebook

## Install Python packages

```bash
sudo apt-get update
sudo apt-get upgrade
pip3 install --user numpy matplotlib jupyter notebook 
pip3 install --user opencv-contrib-python
```

## Connect Raspberry Pi to university wireless network 

Type this in your terminal:
```
sudo nano /etc/wpa_supplicant/wpa_supplicant.conf 
```
 

Edit the contents of the file to the following : 

```
network={ 
    ssid="" 
    priority=1
    proto=RSN 
    key_mgmt=WPA-EAP
    pairwise=CCMP 
    auth_alg=OPEN 
    eap=PEAP 
    identity=""
    password=""
    phase1="peaplabel=0"
    phase2="auth=MSCHAPV2"
}  
```
source: [Connecting a Raspberry Pi 3 to Enterprise WiFi](https://hareshmiriyala.wordpress.com/2018/02/13/connecting-a-raspberry-pi-3-to-enterprise-wifi/).

For the University of Warwick WiFi:
- set *ssid* to *hotspot-secure*, 
- set *identity* to *u**xxxxxxx**@live.warwick.ac.uk* where **xxxxxxx** is your staff number
- set *password* to your university email password

then save the file and restart, it should automatically connect to university WiFi.
