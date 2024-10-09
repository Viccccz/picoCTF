# Description

_#Easy_<br>
_#General_Skills_<br>
_#picoCTF_2021_<br>

Can you look at the data in this binary: [static](../Static_aint't_always_noise/static_aint't_always_noise)? This [BASH script](../Static_aint't_always_noise/static_aint't_always_noise.py) might help!

## Solution

1. Check for the file extension.<br>
   `file static_aint't_always_noise` and `file static_aint't_always_noise.py`
2. Grant executable permission to "static_aint't_always_noise".<br>
   `chmod +x static_aint't_always_noise`
3. Execute both files.<br>
   `./static_aint't_always_noise.py` and `./static_aint't_always_noise`
4. Get the flag.
