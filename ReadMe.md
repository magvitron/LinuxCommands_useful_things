## Activate a virtual env
source ./python_env/bin/activate

## Using vs code in windows PC to edit raspberry pi things
expalining video: https://www.youtube.com/watch?v=-B3t8yYxda4

### commands:
1. Windows:
   - ssh -R 52698:127.0.0.1:52698 pi@192.168.0.104
   - install : Remote VSCode by rafaelmaiolla.remote-vscode in visual studio code
   
2. Rpi:
   - Install rmate (usually with ruby gems) 
   - alias code='rmate -p 52698'
## TroubleShooting:
1. Couldn't connect to TextMate! 
 - in vscode press F1 and select Remote:Stop Server
 - in vscode press F1 and select Remote:Start Server

