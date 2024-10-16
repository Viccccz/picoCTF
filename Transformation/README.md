# Description

_#Easy_<br>
_#Reverse_Engineering_<br>
_#picoCTF_2021_<br>

I wonder what this really is...<br>
''.join([chr((ord(flag[i]) << 8) + ord(flag[i + 1])) for i in range(0, len(flag), 2)])

[Challenge](../Transformation/transformation.enc)

## Solution

1. Unzip folder.
2. Move to drop-in directory.<br>
   `cd drop-in/`
3. Check the file extension.<br>
   `file guessing_game.sh`
4. Execute the file.<br>
   `./guessing_game.sh`
5. Input numbers.<br>
> [!TIP]
> Input the middle number *(range number / 2 = middle number)*

6. Get the flag.

