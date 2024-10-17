# Description

_#Easy_<br>
_#General_Skills_<br>
_#picoCTF_2024_<br>
_#browser_webshell_solvable_<br>
_#git_<br>

My team has been working very hard on new features for our flag printing program! I wonder how they'll ***work together***?

[Challenge](../Collaborative_Development/collaborative_development.zip)

## Solution

1. Unzip folder.
2. Move to drop-in directory.<br>
   `cd drop-in/`
3. Check the file extension.<br>
   `file flag.py`
4. Execute the file.<br>
   `python3 flag.py` or `./flag.py`

> [!IMPORTANT]
> Remember to give executable permission to flag.py before executing the file using `./flag.py`. Command to be used is `chmod +x flag.py`.
   
5. Check if any usable/valuable information from the file.<br>
   `strings flag.py` or `cat flag.py`
6. As there is a team working on this file together, hence we gonna check if there any branch of the file existed.<br>
   `git branch -a`

> [!NOTE]
> The command `git branch -a` is used to display all branches existed.

7. Then, direct to each of the branch to get every parts of the flag.<br>
   `git checkout feature/part-1`
8. Get the flag.<br>
   `strings flag.py` or `cat flag.py`

   ![image](https://github.com/user-attachments/assets/5f1e3ec2-aae5-43d5-a7a6-0dbcb3138d93)

10. Repeat steps 7-9 for each of the branch in order to get the completed flag.

