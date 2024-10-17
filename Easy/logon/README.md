# Description

_#Easy_<br>
_#Web_Exploitation_<br>
_#picoCTF_2019_<br>

The factory is hiding things from all of its users. Can you login as Joe and find what they've been looking at? [https://jupiter.challenges.picoctf.org/problem/13594/](https://jupiter.challenges.picoctf.org/problem/13594/) or http://jupiter.challenges.picoctf.org:13594.

## Solution

1. Right click on the website and enter inspect.
2. Direct to the "Storage" tab and change the cookie "admin" from "False" to "True".
   
   ![image](https://github.com/user-attachments/assets/fe31f6e1-97c8-4fcb-89e1-dc74f8636ee2)

3. Click enter and reload.
4. Get the flag.
