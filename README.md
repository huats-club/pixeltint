# pixeltint
This repository contains the resources needed to execute the STEM Project Pixel Tint <br>

Tested on the following hardware
1. Hardware: Raspberry Pi 4 Model B
2. Operating System: Raspbian Buster Full

## Dependencies

### Pixelizer
The **pixelizer** folder contains two files, namely, **cartoon.py** and **pokeball.png**. **cartoon.py** is a python script that utilizes on the **PILLOW** library to convert an image into a pixelized images with its respective greyscale output. An sample image "**pokeball.png**" has been provided to test out the python script. 

**Sample Output**
![Alt text](Diagram/cartoon%20sample%20output.PNG)

**Installing Pillow Library (with JPEG Support)**
#### download and compile JPEG library
```
wget http://www.ijg.org/files/jpegsrc.v8c.tar.gz    
tar xvfz jpegsrc.v8c.tar.gz
cd jpeg-8c
./configure --enable-shared --prefix=$CONFIGURE_PREFIX
make
sudo make install
```

#### link respective libraries correctly - **Raspberry Pi Only**
```
sudo ln -s /usr/lib/arm-linux-gnueabi/libjpeg.so /usr/lib
sudo ln -s /usr/lib/arm-linux-gnueabi/libfreetype.so /usr/lib
sudo ln -s /usr/lib/arm-linux-gnueabi/libz.so /usr/lib
```

#### install rest of the libraries, as well as freetype and zlib
```
sudo apt-get install libjpeg-dev libfreetype6 libfreetype6-dev zlib1g-dev
```


#### install PILLOW
```
sudo pip3 install pillow 
or 
sudo pip3 install pil
```

### Setting up Imageshow.show() preview
```
sudo apt install imagemagick
```

### MQTT
The **MQTT** folder contain the following python file, **student_pub.py**, where it allows the **raspberry pi** to publish a **MQTT Message** to a broker, "**gateway pi**".

**Installation**
#### Install MQTT client
`sudo apt install -y mosquitto-clients`

#### To run python mqtt script, please install
`sudo pip3 install paho-mqtt`

#### If pip3 is not already installed
`sudo apt install python3-pip`