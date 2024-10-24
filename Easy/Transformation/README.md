# Description

_#Easy_<br>
_#Reverse_Engineering_<br>
_#picoCTF_2021_<br>

I wonder what this really is...<br>
''.join([chr((ord(flag[i]) << 8) + ord(flag[i + 1])) for i in range(0, len(flag), 2)])

[Challenge](Transformation)

## Solution

1. Check the file extension.<br>
   `file Transformation`
2. Decode the text.

> [!TIP]
> [CyberChef](https://gchq.github.io/CyberChef/) using **magic** settings with intensive mode.

3. Get the flag.

