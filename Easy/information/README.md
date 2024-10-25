# Description

_#Easy_<br>
_#Forensics_<br>
_#picoCTF_2021_<br>

Files can always be ***changed*** in a secret way. Can you find the flag? 

[Challenge](information.jpg)

## Solution

1. Check the file extension.<br>
   `file cat.jpg`
2. Get any usable/valuable information from the image.<br>
   `strings cat.jpg` or `cat cat.jpg`
3. Check for its metadata.<br>
   `exiftool cat.jpg`

   ![image](https://github.com/user-attachments/assets/05f4fa3e-ed18-4564-8a9f-5a54983b9f54)

4. Decode the cipher from base64 using [CyberChef](https://gchq.github.io/CyberChef/#recipe=From_Base64('A-Za-z0-9%2B/%3D',true,false)).
5. Get the flag.
