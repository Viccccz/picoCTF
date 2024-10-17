# Description

_#Easy_<br>
_#Web_Exploitation_<br>
_#picoCTF_2021_<br>

Find the flag being held on this server to get ahead of the competition.

## Solution

1. Open BurpSuite.
2. Go to "Proxy" and turn on the intercept.
3. Right click and select "Send to Repeater".
4. Direct to "Repeater" and change the "GET" to "HEAD".

   ![image](https://github.com/user-attachments/assets/695ee02b-fdec-4f45-b3f0-08bb9f1be6fe)

> [!NOTE]
> HEAD request is used to get the **header only**.<br>
> GET request is used to get the **header and body**.

5. Then we'll get the flag on the response section.

   ![image](https://github.com/user-attachments/assets/5ddc5587-925a-454a-a0f6-ddad83fd65f0)
