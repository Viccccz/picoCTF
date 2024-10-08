# Description

_#Easy_<br>
_#Cryptography_<br>
_#picoCTF_2024_<br>
_#base64_<br>
_#browser_webshell_solvable_<br>
_#caesar_<br>

Can you get the real meaning from this file. 

[Challenge](../interencdec/interencdec.pdf)

## Solution

1. Check for the file extension.
   `file enc_flag`
2. Check the file for any human-readable strings or display the whole content.
   `strings enc_flag` or `cat enc_flag`
3. Decode the strings from base64.
4. Remove the "d" in front and then decode again from base64.
5. Decode it with caesar cipher
6. Get the flag.

> [!TIP]
> To decode from base64 [CyberChef](https://gchq.github.io/CyberChef/)<br>
> To decode from Caesar Cipher [cryptii](https://cryptii.com/pipes/caesar-cipher)
