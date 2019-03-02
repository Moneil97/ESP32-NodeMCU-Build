# ESP32-NodeMCU-Build
My Personal NodeMCU Build for ESP32

These instuctions are mostly for my own furture reference

This is what worked for me using Ubuntu 18.04

Building the Firmware:

Linux Dependencies:
sudo apt-get install:
  git
  gcc
  make
  libncurses5-dev
  flex
  bison
  gperf
  python
  python-pip

pip install esptool

git clone --branch dev-esp32 --recurse-submodules https://github.com/nodemcu/nodemcu-firmware.git nodemcu-firmware-esp32

cd nodemcu-firmware-esp32

python -m pip install --user -r ./sdk/esp32-esp-idf/requirements.txt
  
make menuconfig

make

build will be located at: ./build/bootloader.bin
