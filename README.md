# Rpishake Sigfox

How to send a Sigfox message using a RaspberryShake

#### Aim of this script is to control the Sigfox shield to send messages on the SigFox network.

The Sigfox Shield is for Raspberry Pi mainboard and allows to use the [Sigfox network](http://sigfox.com)


### Usage

```
cd sigfox/
python sendsigfox.py CAFE [path/to/serial]
```

- MESSAGE is an HEXA encoded string; 2 to 24 characters representing 1 to 12 bytes.

- Second parameter an the optional path to the serial port, default is /dev/ttyAMA0.

Examples :
- 'sendsigfox 00AA55BF' : sends the 4 bytes 0x00 0xAA 0x55 0xBF
- 'sendsigfox CCDD /dev/ttyS0' : sends the 2 bytes 0xCC 0xDD over /dev/ttyS0

### Prerequist

Disable Raspberry Pi terminal on serial port with raspi-config utility:

sudo raspi-config

9 Advanced Options >> A8 Serial >> NO

Install pyserial

sudo apt-get install python-serial

#### Pi3 requirements

In '/boot/config.txt' disable if present 'dtoverlay=pi3-miniuart-bt' by adding a '\#' character at line begining

Add if necessary :

dtoverlay=pi3-disable-bt

enable_uart=1

Then reboot :

sudo reboot

Serial port to use is the script's default one : /dev/ttyAMA0

## Sigfox Backend

* To see your messages in the Sigfox backend, you can follow the procedure using this Github repository:
https://github.com/Iotnet/Registro-Devkit-IoTnet

* To configure a callback to push your data to an external platform, you can use this repository: https://github.com/Iotnet/Callback

### License

MIT License / read license.txt
