# Description

#Easy<br>
#General_Skills<br>
#picoCTF_2024<br>
#shell<br>
#browser_webshell_solvable<br>
#ls<br>

Want to play a game? As you use more of the shell, you might be interested in how they work! Binary search is a classic algorithm used to quickly find an item in a sorted list. Can you find the flag? You'll have 1000 possibilities and only 10 guesses.
Cyber security often has a huge amount of data to look through - from logs, vulnerability reports, and forensics. Practicing the fundamentals manually might help you in the future when you have to write your own tools!

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

