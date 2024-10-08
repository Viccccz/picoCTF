# Description

_#Easy_<br>
_#Forensics_<br>
_#picoCTF_2024_<br>
_#grep_<br>
_#browser_webshell_solvable_<br>
_#checksum_<br>

People keep trying to trick my players with imitation flags. I want to make sure they get the real thing! I'm going to provide the ***SHA-256 hash*** and a ***decrypt script*** to help you know that my flags are legitimate.

[verify.zip](../Verify/verify.zip)

## Solution

1. Unzip folder.
2. Move to drop-in directory.<br>
   `cd drop-in/`
4. Create SHA checksum of all files in file directory and find for the same checksum with the files in files.<br>
   `sha256sum files/* | grep 'fba9f49bf22aa7188a155768ab0dfdc1f9b86c47976cd0f7c9003af2e20598f7'`
5. Get the file name and decrypt it using decrypt.sh.<br>
   `./decrypt.sh files/<file name>`
6. Get the flag.
