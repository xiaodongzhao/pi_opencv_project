# Use OpenCV and YOLO on Raspberry Pi

## Requirements

- Raspberry Pi Model B (optional)
- Python 3
- Numpy
- OpenCV >= 3.4.2
- Matplotlib
- Jupyter notebook

## Install

### For Windows:

- download and install Python from [anaconda](https://www.anaconda.com/distribution/#download-section).

### For Linux (Ubuntu/Debian/Raspberry Pi)

- open a terminal, update first

```bash
sudo apt-get update
sudo apt-get upgrade
```

### For both Windows and Linux:

- install 

```bash
pip3 install --user numpy matplotlib jupyter notebook 
pip3 install --user opencv-contrib-python
```
- download weights for [YOLO](https://pjreddie.com/media/files/yolov3.weights) and [YOLO-tiny](https://pjreddie.com/media/files/yolov3-tiny.weights).

- clone this repo to a local folder, then open a terminal in the folder and run:

```
jupyter notebook
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
