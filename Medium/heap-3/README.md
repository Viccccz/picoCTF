# Description

_#Medium_<br>
_#Binary_Exploitation_<br>
_#picoCTF_2024_<br>
_#format_string_<br>
_#heap_<br>

This program ***mishandles memory***. Can you exploit it to get the flag?<br>
Download the binary [here](../chall-1).<br>
Download the source [here](../chall.c).

## Solution

Initially, I ran the provided instances. A total of six options were available:

![image](https://github.com/user-attachments/assets/a087c071-80ab-4c07-9e80-5ba7e2e842a6)<br>
**Options given.*

I then tested each option one by one to observe the output. Option 1 displays the heap address and string, Option 2 overwrites the heap address, Option 3 prints the heap address, Option 4 checks for the win condition, Option 5 clears the heap address, and Option 6 exits the program.

By analyzing the source code, we understand that the mission is to overwrite the heap address from 'bico' to ***pico*** in order to obtain the flag.

![image](https://github.com/user-attachments/assets/983d213b-9e72-4427-a99b-dfe41de3f4a5)<br>
**The check_win function in the source code.*

To obtain the flag, we first select Option 5 to reset the heap address to its default state, then select Option 1 to verify the heap address. Next, we choose Option 2 to overflow and overwrite the address by entering 30 'A' characters followed by 'pico', like this: `AAAAAAAAAAAAAAAAAAAAAAAAAAAAAApico`.

> [!TIP]
> After several attempts, I noticed that the system only overwrites the address starting from the 31st character. Therefore, to replace the heap address, we need to input 30 'A' characters followed by the word 'pico'.

To confirm the altered heap address, we can select Option 3 to verify the result. Then, we select Option 4 to execute the check_win function and retrieve the flag.
