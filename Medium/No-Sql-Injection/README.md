# Description

_#Medium_<br>
_#Binary_Exploitation_<br>
_#picoCTF_2024_<br>
_#browser_webshell_solvable_<br>

Can you try to get access to this website to get the flag? You can download the source [here](../app.tar.gz).

## Solution

> [!NOTE]
> - NoSQL injection is an attack similar to SQL injection.
> - It leverages more flexible data formats.
> - Unlike SQL, it does not support structured query language.
> - Data is typically stored and managed as key-value pairs.
> - The attack is most commonly executed by an end-user.
> - Unsanitized input allows the inclusion of malicious content.

Upon reaching the login page, I attempted to log in using a random email and password.<br>

![image](https://github.com/user-attachments/assets/2e25af54-b291-4dbc-b1ad-b794a8725374)<br>
**It displayed a failure message, indicating that the system verified the credentials.*

Next, I attempted to obtain the source file for investigation. I started by using the command `tar -xvf app.tar.gz ./app/` to extract only the ./app/ directory from the app.tar.gz archive.

> [!TIP]
> Command: `tar -xvf app.tar.gz ./app/`<br>
> `-x`: Extract files from the archive.<br>
> `-v`: Show a verbose list of files being extracted.<br>
> `-f`: Specify the archive file to extract from.<br>

I extracted four files from the zipped folder and decided to investigate them one by one in search of any clues for valid credentials.<br>

![image](https://github.com/user-attachments/assets/97707cd0-e433-406d-b3b4-f084d8eaa367)<br>
**These are the extracted files.*

After investigating each of the files, I found that the file ***server.js*** contains of the email used to login to the system.

![image](https://github.com/user-attachments/assets/af9bbb45-5f3a-427c-998b-987b36461904)<br>
**The system stores the credentials of the initial user.*

I then logged into the system using the following credentials:<br>
- Email: ***picoplayer355@picoctf.org***
- Password: ***{"$ne":null}***

> [!IMPORTANT]
> ![image](https://github.com/user-attachments/assets/0435a3dc-feda-4eaa-9de8-c6d3729c4612)<br>
> Access the resources [here](https://hacktricks.boitatech.com.br/pentesting-web/nosql-injection).<br>

I entered the inspect mode of the webpage and navigated to the Network tab to search for more information.

![image](https://github.com/user-attachments/assets/bfe616e5-64b4-44d7-b842-78433678a188)<br>
**There is a token that appears unusual. Based on its pattern, it can be identified as a Base64 cipher.*

Finally, I visited [CyberChef](https://gchq.github.io/CyberChef/) to decrypt the cipher and retrieve the flag.
