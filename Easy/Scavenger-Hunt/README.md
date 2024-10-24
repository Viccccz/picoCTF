# Description

_#Easy_<br>
_#Web_Exploitation_<br>
_#picoCTF_2021_<br>

There is some interesting information hidden around this site. Can you find it?

## Solution

1. Right click on the website and enter view page source.

   ![image](https://github.com/user-attachments/assets/5d056bb4-d1a0-4c16-9b07-9e2270eae89c)

2. Get a part of the flag.
3. Then, we direct to css file and get the second part of the flag.

   ![image](https://github.com/user-attachments/assets/74f79392-d15b-479e-aa6a-2e28a3ddac6a)

4. After directing to the script file, we noticed there is a hint for the next part of flag.

   ![image](https://github.com/user-attachments/assets/407996b0-052d-4811-9dcb-f060beb384a8)

> [!NOTE]
> To prevent Google from indexing websites, there is always a txt file named "robots.txt".

5. So we can manually change the url to `/robots.txt` to get the third part of teh flag.

   ![image](https://github.com/user-attachments/assets/fa582f03-b8e7-4486-9b16-e8cb53586ba1)

   - There is also a hint for the nxt part of flag.

> [!NOTE]
> To access to the apache server, we can change the directory to "/.htacess"

6. Change the file to .htaccess to get the flag.

   ![image](https://github.com/user-attachments/assets/ff3921ea-5c84-44d4-bd29-dcb1eccbb347)

> [!NOTE]
> To access to the apache server, we can change the directory to "/.DS_Store"

7. Change the file to .DS_Store to get the flag.

   ![image](https://github.com/user-attachments/assets/befc0c8b-7882-4909-b2fa-ec2c626fbefd)

