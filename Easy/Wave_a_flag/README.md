# Description

_#Easy_<br>
_#General_Skills_<br>
_#picoCTF_2021_<br>

Can you invoke help flags for a tool or binary? [This program](../Wave_a_flag/wave_a_flag) has extraordinarily helpful information...

## Solution

1. Check the file extension.<br>
   `file warm`
2. Grant permission to run the file.<br>
   `chmod +x warm`
3. Execute the file.<br>
   `./warm`

   ![image](https://github.com/user-attachments/assets/0dd5a7af-3166-492f-8bca-4d6b82abfb2e)

4. Input some command to see the result.

   ![image](https://github.com/user-attachments/assets/831c607a-2d7a-4d02-a9c8-24092ad0e692)

5. Get the flag.

   ![image](https://github.com/user-attachments/assets/81e418a6-61e2-41c3-a6a0-b7d5fb7f1363)
