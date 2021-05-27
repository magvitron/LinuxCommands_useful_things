# Raspberry pi stuffs and python stuffs
## Set encoding for python
```
# -*- coding: utf-8 -*-
```

## Tensor flow how to do link:
https://github.com/EdjeElectronics/TensorFlow-Lite-Object-Detection-on-Android-and-Raspberry-Pi/blob/master/Raspberry_Pi_Guide.md#part-1---how-to-set-up-and-run-tensorflow-lite-object-detection-models-on-the-raspberry-pi

## Kill process with a PID
```
PID_val=$(ps -C "python3" -o pid=)
kill -KILL $PID_val
python3 cam_detect.py
```
use an sh for calling this.

## list all process:
```
htop
```
kill process:
```
kill -KILL PID
```

## Secure file copy or SCP for Pi to windows file copying
- Link: https://www.raspberrypi.org/documentation/remote-access/ssh/scp.md
Copying files to your Raspberry Pi
```
scp myfile.txt pi@192.168.1.3:
```
Copying files from your Raspberry Pi
```
scp pi@192.168.1.3:myfile.txt .
```
## Tensor Flow
### Pi-Zero precompiled binary 
```
https://github.com/lhelontra/tensorflow-on-arm/releases
```
Use the below code for taking values
```
import tensorflow as  tf

print(str(tf.__version__)) # should print the version
interpreter = tf.lite.Interpreter(model_path) # for example if you just need the python tf lite runtime 
```
## Activate a virtual env
```
source ./python_env/bin/activate
```

## Using vs code in windows PC to edit raspberry pi things
expalining video: https://www.youtube.com/watch?v=-B3t8yYxda4

### commands:
1. Windows:
 ```
 ssh -R 52698:127.0.0.1:52698 pi@192.168.0.104
 ```
 ```
 install : Remote VSCode by rafaelmaiolla.remote-vscode in visual studio code
 ```
2. Rpi:
   - Install rmate (usually with ruby gems) 
   ```
   alias code='rmate -p 52698'
   ```
### TroubleShooting:
1. Couldn't connect to TextMate! 
 - in vscode press F1 and select Remote:Stop Server
 - in vscode press F1 and select Remote:Start Server


## STM 32 Clone chips debugging
However, if you do end up with one, there is a way to get it working with OpenOCD. >>

1.   Use OpenOCD as your debugger (GDB will not work)

2.   Find the config file : stm32f1x.cfg

Location is similar to this : >>

C:\ST\STM32CubeIDE_1.3.0\STM32CubeIDE\plugins\com.st.stm32cube.ide.mcu.debug.openocd_1.3.0.202002181050\resources\openocd\st_scripts\target

3.   Add the following near the top of stm32f1x.cfg (before the first If – statement):

set CPUTAPID 0

The zero tells OpenOCD to ignore id numbers, which means all clones or genuine MCUs will work.

4.     Save the changes. Now your flash and debug should work. 

 

Note: If you change to OpenOCD without changing “stm32f1x.cfg”, you will get the following Error: “UNEXPECTED idcode: 0x2ba01477…. Expected: 0x1ba01477”, and you will again be stuck.

Information Source: http://openocd.org/doc/html/TAP-Declaration.html#TAP-Declaration-Commands

