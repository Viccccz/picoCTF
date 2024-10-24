# Description

_#Easy_<br>
_#Forensics_<br>
_#picoCTF_2024_<br>
_#shell_<br>
_#browser_webshell_solvable_<br>
_#qrcode_<br>

I've gotten bored of handing out flags as text. Wouldn't it be cool if they were an image instead?

[Challenge](Scan-Surprise.zip)

## Solution

1. Unzip folder.
2. Move to drop-in directory.<br>
   `cd drop-in/`
3. Check the file extension.<br>
   `file flag.png`
4. Check for the image data and find for any human readable strings.<br>
   `strings flag.png` or `cat flag.png`
5. Open image.<br>
   `eog flag.png`
6. Scan the QR code using any online QR code reader.
7. Get the flag.
