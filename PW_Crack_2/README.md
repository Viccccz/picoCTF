# Description

_#Easy_<br>
_#General_Skills_<br>
_#Begineer_picoMini_2022_<br>
_#password_cracking_<br>

Can you crack the password to get the flag?
Download the password checker [here](../PW_Crack_2/pw_crack_2.py) and you'll need the encrypted [flag](../PW_Crack_2/pw_crack_2.enc) in the same directory too.

## Solution

1. Execute the "pw_crack_2.py".<br>
   `python3 pw_crack_2.py`

> [!IMPORTANT]
> Remember to install the package using `sudo apt install python3` before executing the script.

2. We can see there are hexadecimal values for the password.
   
   ![image](https://github.com/user-attachments/assets/f641ad40-48b5-4646-a323-067bb7ededb7)

   - From the source code, we can convert from hexadecimal. [CyberChef](https://gchq.github.io/CyberChef/)
   - Answer is ***4ec9***

3. Input the password and we'll get the flag.
