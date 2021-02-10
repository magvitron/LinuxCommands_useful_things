# Raspberry pi stuffs 
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
 
## install a .so file in library
Something to do with ld config , needs investigation.
