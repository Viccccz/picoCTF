# Description

_#Easy_<br>
_#General_Skills_<br>
_#picoCTF_2024_<br>
_#browser_webshell_solvable_<br>
_#git_<br>

What was I last working on? I remember writing a note to help me remember...

[scan_surprise.zip](../Scan_Surprise/scan_surprise.zip)

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

