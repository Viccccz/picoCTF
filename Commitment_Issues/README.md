# Description

_#Easy_<br>
_#General_Skills_<br>
_#picoCTF_2024_<br>
_#browser_webshell_solvable_<br>
_#git_<br>

I accidentally wrote the flag down. Good thing I ***deleted*** it!

[Challenge](../Commitment_Issues/commitment_issues.zip)

## Solution

1. Unzip folder.
2. Move to drop-in directory.<br>
   `cd drop-in/`
3. Check the file extension.<br>
   `file message.txt`
4. Try gaining usable information from the file.<br>
   `strings messgae.txt` or `cat message.txt`
5. Check the previous version of file.<br>
   `git log messgae.txt`
6. Restore the file to the specific version we want.<br>
   `git checkout b562f0b425907789d11d2fe2793e67592dc6be93`
   
   ![image](https://github.com/user-attachments/assets/66afd34f-9437-46fe-aabc-76c4cf85a766)

8. Get the flag.

