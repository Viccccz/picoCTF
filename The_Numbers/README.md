# Description

_#Easy_<br>
_#Cryptography_<br>
_#picoCTF_2019_<br>

The numbers... what do they mean?

[Challenge](../The_Numbers/the_numbers.png)

## Solution

1. Check the file extension.<br>
   `file the_numbers.png`
2. Get the metadata (to see if any usable/valuable information).<br>
   `exiftool the_numbers.png` or `cat the_numbers.png` or `strings the_numbers.png`
3. Open the image.<br>
    `eog the_numbers.png`
4. Decode the numbers using [CyberChef](https://gchq.github.io/CyberChef/) using **magic** setting with intensive mode.
5. Get the flag.

