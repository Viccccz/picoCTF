# Description

_#Easy_<br>
_#General_Skills_<br>
_#picoGym_Exclusive_<br>

Unzip this archive and find the flag.

[Challenge](../Big_Zip/big_zip.zip)

## Solution

1. Unzip folder.<br>
2. Move to drop-in directory.<br>
   `cd big-zip-files/`
3. As there are many files and folders and we are unable to check one by one, hence we will use grep to search for the keyword "pico" in order to find the flag.<br>
   `grep -r big-zip-files -e pico`

> [!NOTE]
> -r is used to search recursively, meaning that it will search through all files in the specific directories and its subdirectories.<br>
> -e is used to define the pattern to search for.
   
4. Get the flag.
