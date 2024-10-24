# Description

_#Easy_<br>
_#General_Skills_<br>
_#picoCTF_2021_<br>

Can you look at the data in this binary: [static](Static-aint't-always-noise)? This [BASH script](Static-aint't-always-noise.py) might help!

## Solution

1. Check for the file extension.<br>
   `file Static-aint't-always-noise` and `file Static-aint't-always-noise.py`
2. Grant executable permission to "static_aint't_always_noise".<br>
   `chmod +x Static-aint't-always-noise`
3. Execute both files.<br>
   `./Static-aint't-always-noise.py` and `./Static-aint't-always-noise`
4. Get the flag.
