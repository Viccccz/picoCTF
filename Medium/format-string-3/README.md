# Description

_#Medium_<br>
_#Binary_Exploitation_<br>
_#picoCTF_2024_<br>
_#format_string_<br>
_#browser_webshell_solvable_<br>

This program doesn't contain a win function. How can you win?<br>
Download the binary [here](format-string-3).<br>
Download the source [here](format-string-3.c).<br>
Download libc [here](libc.so.6), download the interpreter [here](ld-linux-x86-64.so.2). Run the binary with these two files present in the same directory.

## Solution

1. We first grant executable permission to both binary and interpreter file.<br>
   `chmod +x format-string-3 ld-linux-x86-64.so.2`

2. Then, run the binary file to investigate the output and find out vulnerabilities.<br>
   `./format-string-3`

   ![image](https://github.com/user-attachments/assets/ddb07337-8413-422b-bd0e-68d678e620bd)<br>
   *Note: After trying some inputs, it outputs some different answer. To read arbitrary stack values, input [format specifiers](https://unstop.com/blog/format-specifiers-in-c) such as %f (float) or %p (pointer).*

3. After finding out the problem of the source code, we can exploit it to get the flag.

> [!IMPORTANT]
> Key information users need to know to achieve their goal.
