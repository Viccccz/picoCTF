# Description

_#Easy_<br>
_#General_Skills_<br>
_#picoCTF_2024_<br>
_#browser_webshell_solvable_<br>
_#git_<br>

Someone's commits seems to be preventing the program from working. Who is it?

[Challenge](../Binary_Search/binary_search.zip)

## Solution

1. Unzip folder.
2. Move to drop-in directory.<br>
   `cd drop-in/`
3. Check the file extension.<br>
   `file message.py`
4. Execute the file.<br>
   `python3 messgae.py`
5. Check the restore version of the file.
   `git log message.py`
6. Get the flag.
   
   ![image](https://github.com/user-attachments/assets/9fbe1fd8-09a7-4aaa-a64d-5985ab0dbcf5)
