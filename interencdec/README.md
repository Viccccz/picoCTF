# Description

_#Easy_<br>
_#Cryptography_<br>
_#picoCTF_2024_<br>
_#base64_<br>
_#browser_webshell_solvable_<br>
_#caesar_<br>

Can you get the real meaning from this file. 

[interencdec.pdf](../interencdec/interencdec.pdf)

## Solution

1. Open BurpSuite.
2. Fill in the registration form.
3. Navigate to the proxy page and and turn on the intercept.
   ![image](https://github.com/user-attachments/assets/88fe3d41-4042-488b-a252-32dc10103b97)

4. Submit registration form and click "forward" in BurpSuite to forward it to proceed.
5. Then, input any number for the 2FA code.
6. We'll now see there is a line of code appears in the BurpSuite.
7. Remove the line and click "forward".
8. Get the flag.

> [!IMPORTANT]
> This is only for those who are using BurpSuite browser extension.
> For those who are using BurpSuite software, the procedures are similar and can try research online if any unclear about the usage of it.

> [!NOTE]
> Remember to turn on the intercept before submitting any requests.

