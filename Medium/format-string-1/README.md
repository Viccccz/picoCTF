# Description

_#Medium_<br>
_#Binary_Exploitation_<br>
_#picoCTF_2024_<br>
_#format_string_<br>
_#browser_webshell_solvable_<br>

Patrick and Sponge Bob were really happy with ***those orders you made for them***, but now they're curious about the ***secret menu***. Find it, and along the way, maybe you'll find something else of interest!
Download the binary [here](../format-string-1).
Download the source [here](../format-string-1.c).

## Solution

1. Connect with the challenge instance.
2. Insert many `%p` to retrieve the memory address from the system.

   ![image](https://github.com/user-attachments/assets/8fcde7a9-44c9-4539-b7a6-8d0d8e9dd459)

3. Use the [CyberChef](https://gchq.github.io/CyberChef/) to convert the output to make sense of it.
4. Then, we'll realize that the flag might be included in the 14th to 18th memory addresses.

   ![image](https://github.com/user-attachments/assets/4ee7ec2c-73e2-4604-b104-2f6ac35718e4)
   
5. Re-arrange the memory addresses regarding to the little-endian order using [calculator online](https://www.save-editor.com/tools/wse_hex.html).
6. Convert the result from hexadecimal.
7. Get the flag.
    
