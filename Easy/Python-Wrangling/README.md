# Description

_#Easy_<br>
_#General_Skills_<br>
_#picoCTF_2021_<br>

Python scripts are invoked kind of like programs in the Terminal... Can you run this [Python script](Python-Wrangling.py) using this [password](Python-Wrangling.txt) to get the [flag](Python-Wrangling.en)?

## Solution

1. First open the python script to understand the source code.
2. We found that it is used to decrypt a file named "pole.txt". So we rename our "Python-Wrangling.en" to "pole.txt".
3. Then, we run the python script with the file "pole.txt".<br>
   `python3 Python-Wrangling.py -d pole.txt`
4. Get the password from "Python-Wrangling.txt" and enter to decrypt the file.
5. Get the flag.
