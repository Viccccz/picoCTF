# Description

_#Easy_<br>
_#General_Skills_<br>
_#picoCTF_2021_<br>

Do you know how to ***move between directories*** and read files in the shell? Start the container, `ssh` to it, and then `ls` once connected to begin. Login via `ssh` as `ctf-player` with the password, `ee388b88`

## Solution

1. Login via ssh as "ctf-player" with password "ee388b88".<br>
   `ssh ctf-player@venus.picoctf.net -p 51708`
2. Enter yes.
3. Input the password.
4. Display all directories existed in the system.<br>
   `ls`
5. Get the part of flag from 1of3.flag.txt.<br>
   `cat 1of3.flag.txt`
6. Then direct to the parent directory to look for more files.<br>
   `cd ..`
7. Repeat steps 4-6 if needed in order to find all the flags.
