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

