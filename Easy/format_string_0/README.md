# Description

_#Easy_<br>
_#Binary_Exploitation_<br>
_#picoCTF_2024_<br>
_#browser_webshell_solvable_<br>
_#format_string_<br>

Can you use your knowledge of ***format strings*** to make the customers happy?<br>

Download the binary. [here](../format_string_0/format_string_0)<br>
Download the source. [here](../format_string_0/format_string_0.c)

## Solution

> [!TIP]
> Look into the source code!

1. Recommendation for 1st customer: :speech_balloon:
![image](https://github.com/user-attachments/assets/fcff728b-a9f7-4c46-ba3c-71c019ccf43b)

   - When looking into the source code<br>
![image](https://github.com/user-attachments/assets/c3493633-035a-4ab5-8507-1bddaff16dc1)

      - `if (count > 2 * BUFSIZE)` -> checks if the printed characters exceed 64 bytes (since BUFSIZE is defined as 32 bytes)<br>
      - So the answer is __Gr%114d_Cheese__ because it has 13 character and can print 144 characters when printing `%114d`
      - Therefore, __Gr%114d_Cheese__ can be used to overflow the variable and hence proceed to next question.

2. Recommendation for 2nd customer: :speech_balloon:
![image](https://github.com/user-attachments/assets/6b3e5d83-39e5-4517-8a24-4d8678542a24)

   - When looking into the options given, only __Cla%s%steak__ is the one which contains `%s` that is used to printf valid strings.<br>
