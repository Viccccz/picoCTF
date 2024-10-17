# Description

_#Easy_<br>
_#Web_Exploitation<br>
_#picoCTF_2021_<br>

Who doesn't love cookies? Try to figure out the best one.

## Solution

1. Open BurpSuite.
2. Try input any type of cookies in the browser and submit.
3. Right click on the website to open inspect.
4. We observed that if our input is correct, the cookies "name" will be set to 0. If not, it will be set to -1.
   
   ![image](https://github.com/user-attachments/assets/ee54274b-7100-4292-8e2f-09eb077485be)

   ![image](https://github.com/user-attachments/assets/7aa266e9-fa32-485c-acc5-7cb2a3dda0f9)

5. We noticed that the "content-length" is set to 18, so we need to change the cookie "name" to 18 to get the flag.

   ![image](https://github.com/user-attachments/assets/86fc0ca5-069b-4f22-a0d7-233bdb6af281)
   
   ![image](https://github.com/user-attachments/assets/a1df7310-9015-45dc-98a8-f3a68ee6d5f9)

7. Get the flag.
   
   ![image](https://github.com/user-attachments/assets/af3e623b-4e93-4f46-8ab0-638bb1a46be1)
