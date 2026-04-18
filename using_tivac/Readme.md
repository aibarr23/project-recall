# Using tiva C for embedded development with no IDE

refs:
CMake and lm4tools for TM4C123 Development Board

by Yusef Karim & Waun Broderick

Tutorial here:

https://www.hackster.io/tcss/upload-code-to-ti-tm4c123-using-linux-cmake-and-lm4tools-c33cec

source code here:
https://gitlab.com/yusefkarim/cmake-tm4c-blinky

## Building and uploading our code

we can use CMake files to create a Make file that can compile and
upload the code directly to our board.

Make sure your board is plugged in and switched on for these steps.

```bash
mkdir build
cd build
cmake ..
make
sudo make flash
```

NOTE: if the last command does not work try bellow instead
and the link for more information on how tofix it

```bash
sudo env PATH=$PATH make flash
```

## IMPORTANT connecting devices ICDI from wsl with windows

## try this when Unable to find any ICDI devices

list usb devices

```powershell
usbipd list
```

bind(share) and attach device

```powershell
usbipd bind --busid <busid>
usbipd attach --wsl --busid <busid>
```

verify in WSL

```bash
lsusb
```

### not sure what it is for need looking into

kernel messages when plugging in the devices
for logging/monitor

```bash
dmesg -w
```
