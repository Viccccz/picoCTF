# Description

_#Easy_<br>
_#Forensics_<br>
_#picoCTF_2024_<br>
_#file_format_<br>
_#polyglot_<br>

The Network Operations Center (NOC) of your local institution picked up a suspicious file, they're getting conflicting information on what type of file it is. They've brought you in as an external expert to examine the file. Can you extract all the information from this strange file?

[secret_of_the_polyglot.pdf](../Secret_of_the_Polyglot/secret_of_the_polyglot.pdf)

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

