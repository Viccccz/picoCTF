# Description

_#Easy_<br>
_#Binary_Exploitation_<br>
_#picoCTF_2024_<br>
_#browser_webshell_solvable_<br>
_#heap_<br>

Are ***overflows*** just a stack concern?<br>

Download the binary. [here](../heap_0/heap_0)<br>
Download the source. [here](../heap_0/heap_0.c)

## Solution

### Heap  
An Area of pre-reserved computer main storage (memory) that a program process can use to store data.<br>
In this case, we need to overflow the memory and hence it display the flag.<br>

1. Select option __1__ to check for the heap state.
2. Select option __2__ to write something to overflow it.<br>
> [!TIP]
> The position that we can write is 0x63c3882552b0.<br>
  The position of the variable is shown to be corrupted in 0x63c3882552d0.<br>
  Substracting this two position could gives us 0x20, or 32 in decimal.<br>
  Hence, we need to input a 33 byte string without spaces.
   
4. Select option __4__ to get the flag.

