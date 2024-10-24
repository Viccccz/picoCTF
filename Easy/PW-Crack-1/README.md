# Description

_#Easy_<br>
_#General_Skills_<br>
_#Begineer_picoMini_2022_<br>
_#password_cracking_<br>

Can you ***crack the password*** to get the flag?<br>
Download the password checker [here](PW-Crack-1.py) and you'll need the encrypted [flag](PW-Crack-1.enc) in the same directory too.

## Solution

1. Get the usable/valuable information from "pw_crack_1.py".<br>
   `strings PW-Crack-1.py` or `cat PW-Crack-1.py`

> [!IMPORTANT]
> Remember to install the package using `sudo apt install python3` before executing the script.

2. We can see there is a password shown.
   
   ![image](https://github.com/user-attachments/assets/6c560c9d-44e2-4dca-9de8-a822f3b33869)

   - Answer is ***8713***

3. Input the password and we'll get the flag.
