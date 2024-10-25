# Description

_#Easy_<br>
_#General_Skills_<br>
_#picoCTF_2024_<br>
_#base64_<br>

Can you make sense of this file?

[Challenge](repetitions)

## Solution

1. Unzip folder.
2. Move to drop-in directory.<br>
   `cd drop-in/`
3. Check the file extension.<br>
   `file enc_flag`
4. Get any usable/valuable information from the file.<br>
   `strings enc_flag` or `cat enc_flag`
5. Decode the flag from base64 until we get the flag.

> [!TIP]
> [Base64 Decoder](https://www.base64decode.org/)
