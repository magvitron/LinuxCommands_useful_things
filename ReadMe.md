## SCP 
- Link: https://www.raspberrypi.org/documentation/remote-access/ssh/scp.md
Copying files to your Raspberry Pi
```
scp myfile.txt pi@192.168.1.3:
```
Copying files from your Raspberry Pi
```
scp pi@192.168.1.3:myfile.txt .
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
ldconfig creates, updates, and removes the necessary links and cache (for use by the run-time linker, ld.so) to the most recent shared libraries found in the directories specified on the command line, in the file /etc/ld.so.conf, and in the trusted directories (/usr/lib and /lib).

So, assuming that freeverb.so is located in /home/yourUser/Download directory (folder), create folder in your home:

   mkdir /home/yourUser/myLibrary
and copy freeVerb.so library:

   cp /home/yourUser/Download/freeverb.so /home/yourUser/myLibrary
create a simple file freeverb.conf like this:

   echo "/home/yourUser/myLibrary" > freeverb.conf
Add you configuration file freeverb.conf in /etc/ld.so.conf.d directory (in this directory you can find files as example)

   sudo cp freeverb.conf /etc/ld.so.conf.d
Run ldconfig in order to configure dynamic linker run-time bindings.

   sudo ldconfig
If /etc/ld.so.conf.d doesn't exists, you can add your path at the end of /etc/ld.so.conf file.

At the end, if all went well, you can remove unnecessary file:

   rm freeverb.conf
   rm /home/yourUser/Download/freeverb.so

 
Related Question
Ubuntu – How to install JRE on Ubuntu
U
