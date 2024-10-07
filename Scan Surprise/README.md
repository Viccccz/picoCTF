# Description

#Easy<br>
#Forensics<br>
#picoCTF_2024<br>
#shell<br>
#browser_webshell_solvable<br>
#qr_code<br>

I've gotten bored of handing out flags as text. Wouldn't it be cool if they were an image instead?

[scan_surprise.zip](../Scan Surprise/scan_surprise.zip)

## Solution

1. Unzip folder
2. Move to drop-in directory<br>
   `cd drop-in/`
4. Create SHA checksum of all files in file directory and find for the same checksum.<br>
   `sha256sum files/* | grep 'fba9f49bf22aa7188a155768ab0dfdc1f9b86c47976cd0f7c9003af2e20598f7'`
5. Get the file name and decrypt it using decrypt.sh.<br>
   `./decrypt.sh files/<file name>`
6. Get the flag.
