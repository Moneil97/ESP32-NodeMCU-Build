# ESP32-NodeMCU-Build
My Personal NodeMCU Build for ESP32

These instuctions are mostly for my own furture reference

This is what worked for me using Ubuntu 18.04

## Building the Firmware:

### Linux Dependencies:

sudo apt-get install
  git
  gcc
  make
  libncurses5-dev
  flex
  bison
  gperf
  python
  python-pip

### Install ESP Tool

pip install esptool

### Clone the Firmware

git clone --branch dev-esp32 --recurse-submodules https://github.com/nodemcu/nodemcu-firmware.git nodemcu-firmware-esp32

cd nodemcu-firmware-esp32

### Install Python requirements

python -m pip install --user -r ./sdk/esp32-esp-idf/requirements.txt
 
### Configure the build

make menuconfig

### Build

make

Build will be located at: ./build/bootloader.bin

## Flashing Firmware

### Place ESP32 in Boot Mode

1. Connect GPIO-0 to GND (holding IO0 button didn't work for me)
2. Plug ESP32 into computer

![alt text](https://cdn.instructables.com/FOL/YWLI/JEOILQ5U/FOLYWLIJEOILQ5U.LARGE.jpg "ESP32 Dev Kit Pinout")



### Flash

While still in the nodemcu-firmware-esp32 directory: sudo make flash
