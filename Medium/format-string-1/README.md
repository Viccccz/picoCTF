# Description

_#Medium_<br>
_#Binary_Exploitation_<br>
_#picoCTF_2024_<br>
_#format_string_<br>
_#browser_webshell_solvable_<br>

Patrick and Sponge Bob were really happy with those orders you made for them, but now they're curious about the secret menu. Find it, and along the way, maybe you'll find something else of interest!
Download the binary [here](../).
Download the source [here](../).

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
