# Description

_#Easy_<br>
_#Forensics_<br>
_#picoCTF_2024_<br>
_#browser_webshell_solvable_<br>

How about some hide and seek?

[Challenge](../CanYouSee/canyousee.zip)

## Solution

1. Unzip folder.
2. Check the file extension.<br>
   `file ukn_reality.jpg`
4. Get any usable/valuable information from the image.<br>
   `strings ukn_reality.jpg` or `cat ukn_reality.jpg`
5. Try extract any information from the image.<br>
   `steghide extract -sf ukn_reality.jpg` or `stegseek ukn_reality.jpg`
6. After stegseeking the image, we'll get a new file named "ukn_reality.jpg.out".<br>
7. Then we open the file content.<br>
   `strings ukn_reality.jpg.out` or `cat ukn_reality.jpg.out`

   ![image](https://github.com/user-attachments/assets/be935a4f-d0e0-44a0-bb9d-2eb75271dd43)

   It tells us the flag is not here, and maybe we should think it simpler.

8. Then we can extract the metadata of the image.
   `exiftool ukn_reality.jpg`
9. We'll then get a base64 cipher and try to decode it.
    
    ![image](https://github.com/user-attachments/assets/d67fd94d-cdf9-40bf-9887-ab0aef89e769)

10. After decode, we'll get the flag.
