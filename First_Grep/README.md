# Description

_#Easy_<br>
_#General_Skills_<br>
_#picoCTF_2019_<br>

Can you find the flag in [file](../First_Grep/first_grep)? This would be really tedious to look through manually, something tells me there is a better way.

## Solution

1. Check the file extension.<br>
   `file first_grep`
2. Find any usable/valuable data from the file.<br>
   `cat first_grep | grep "pico"`
3. Get the flag.

