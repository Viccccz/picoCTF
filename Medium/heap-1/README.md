# Description

_#Medium_<br>
_#Binary_Exploitation_<br>
_#picoCTF_2024_<br>
_#browser_webshell_solvable_<br>
_#heap_<br>

Can you control your ***overflow***?<br>
Download the binary [here](../chall).<br>
Download the source [here](../chall.c).

## Solution

This challenge is an evolved version of [heap 0](../../Easy/heap-0/README.md) from the easy category. To kick off the challenge, we need to examine the source code to identify the condition for obtaining the flag.

![image](https://github.com/user-attachments/assets/d2f35a30-dd13-4b17-88ef-ca53619bb15d)<br>
**From this section, we can see that we need to modify the value of safe_var to "pico" in order to obtain the flag.*

Now that we know the required condition, we can execute the code.

![image](https://github.com/user-attachments/assets/06dbfcc1-dac4-4143-a3f7-bf633231aeaf)<br>
**From the table, we can observe that the addresses for "pico" and "bico" are the same. This means we can buffer the changeable addresses by using 32 bytes.*

To meet the given condition, we first input numbor ***2*** to write to the buffer by entering 32 random characters, which resulted in the word ***pico***.

![image](https://github.com/user-attachments/assets/e9b8f3f7-1172-4a68-8559-d3d24ec6f3d9)<br>
**The result shown.*

To verify, we input the number ***4*** to display the result and check if we obtained the flag.

![image](https://github.com/user-attachments/assets/1b1ce347-9a16-4486-8f77-f750c1c4471b)<br>
**The flag.*
