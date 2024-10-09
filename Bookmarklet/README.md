# Description

_#Easy_<br>
_#Web_Exploitation_<br>
_#picoCTF_2024_<br>
_#obfuscation_<br>
_#browser_webshell_solvable_<br>
_#browser_<br>

Why search for the flag when I can make a bookmarklet to print it for me?

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

