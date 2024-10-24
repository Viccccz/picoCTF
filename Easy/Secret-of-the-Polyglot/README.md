# Description

_#Easy_<br>
_#Forensics_<br>
_#picoCTF_2024_<br>
_#file_format_<br>
_#polyglot_<br>

The Network Operations Center (NOC) of your local institution picked up a suspicious file, they're getting conflicting information on ***what type of file*** it is. They've brought you in as an external expert to examine the file. Can you ***extract*** all the information from this strange file?

[Challenge.pdf](Secret-of-the-Polyglot.pdf)

## Solution

1. Download the given pdf.
2. Check the file extension.<br>
   `file flag.pdf`
3. Change the file extension to png.<br>
   `mv flag.pdf flag.png`
4. Open the png file.<br>
   `eog flag.png`
5. Combine two flags together and we'll get the completed flag.<br>
