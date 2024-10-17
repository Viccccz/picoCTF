# Description

_#Medium_<br>
_#Binary_Exploitation_<br>
_#picoCTF_2024_<br>
_#format_string_<br>
_#browser_webshell_solvable_<br>

This program doesn't contain a win function. How can you win?<br>
Download the binary [here](../format_string_3/format_string_3).<br>
Download the source [here](../format_string_3/format_string_3).<br>
Download libc [here](../format_string_3/format_string_3), download the interpreter [here](../format_string_3/format_string_3). Run the binary with these two files present in the same directory.

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
