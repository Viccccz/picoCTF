# Description

#Easy<br>
#Web_Exploitation<br>
#picoCTF_2024<br>
#obfuscation<br>
#browser_webshell_solvable<br>

I don't like scrolling down to read the code of my website, so I've squished it. As a bonus, my pages load faster!

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

