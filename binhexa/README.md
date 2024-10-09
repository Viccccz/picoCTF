# Description

_#Easy_<br>
_#General_Skills_<br>
_#picoCTF_2024_<br>
_#browser_webshell_solvable_<br>

How well can you perfom basic ***binary operations***?

## Solution

Example Binary Number 1: 10110011<br>
Example Binary Number 2: 00111101 

1. Operation: ">>"<br>
   - Perform a **right shift** of binary number 2 by 1 bits.<br>
   - `00111101` -> `00011110`<br>
   - The last digit `0` is removed and add one `0` in front.
   - Answer is ***00011110***
  
2. Operation: "+"<br>
   - Perform **addition** on binary number 1 and 2.<br>
   
     | + Operation  | 
     |:------------:|
     |   10110011   |
     |   00111101   |
     |--------------|
     |   11110000   |

   - Answer is ***11110000***

3. Operation: "<<"<br>
   - Perform a **left shift** of binary number 1 by 1 bits.<br>
   - `00111101` -> `001111010`<br>
   - Add one `0` as the last digit.
   - Answer is ***001111010***

4. Operation: "|"<br>
   - Perform **OR operation** on binary number 1 and 2.<br>
   
     |  OR Operation | 
     |:-------------:|
     |    10110011   |
     |    00111101   |
     |---------------|
     |    10111111   |

   - Answer is ***10111111***

5. Operation: "*"<br>
   - Perform a **multiplication** on binary number 1 and 2.<br>

     |    * Operation     | 
     |:------------------:|
     |      10110011      |
     |      00111101      |
     |--------------------|
     |   10101010100111   |
   
   - Answer is ***10101010100111***
  
6. Operation: "&"<br>
   - Perform **ADD operation** on binary number 1 and 2.<br>
   
     |  ADD Operation  | 
     |:---------------:|
     |     10110011    |
     |     00111101    |
     |-----------------|
     |     00110001    |

   - Answer is ***00110001***

7. Result of last answer in hexadecimal: ***31***

> [!TIP]
> [Binary Calculator](https://www.calculator.net/binary-calculator.html)
> [Binary to Hex Converter](https://www.rapidtables.com/convert/number/binary-to-hex.html)

----------------------------------------------------------------------------------------------------------------------------

Example Binary Number 1: 11100010<br>
Example Binary Number 2: 00101111 

1. Operation: ">>"<br>
   - Perform a **right shift** of binary number 2 by 1 bits.<br>
   - `00101111` -> `00010111`<br>
   - The last digit `1` is removed and add one `0` in front.
   - Answer is ***00010111***
  
2. Operation: "<<"<br>
   - Perform a **left shift** of binary number 1 by 1 bits.<br>
   - `11100010` -> `111000100`<br>
   - Add one `0` as the last digit.
   - Answer is ***111000100***
  
3. Operation: "+"<br>
   - Perform **addition** on binary number 1 and 2.<br>
   
     |  + Operation  | 
     |:-------------:|
     |    11100010   |
     |    00101111   |
     |---------------|
     |   100010001   |

   - Answer is ***100010001***

4. Operation: "|"<br>
   - Perform **OR operation** on binary number 1 and 2.<br>
   
     |  OR Operation  | 
     |:--------------:|
     |    11100010    |
     |    00101111    |
     |----------------|
     |    11101111    |

   - Answer is ***11101111***

5. Operation: "&"<br>
   - Perform **ADD operation** on binary number 1 and 2.<br>
   
     | ADD Operation  | 
     |:--------------:|
     |    11100010    |
     |    00101111    |
     |----------------|
     |    00100010    |

   - Answer is ***00100010***
  
6. Operation: "*"<br>
   - Perform a **multiplication** on binary number 1 and 2.<br>

     |    * Operation     | 
     |:------------------:|
     |      11100010      |
     |      00101111      |
     |--------------------|
     |   010100101111110   |
   
   - Answer is ***010100101111110***

7. Result of last answer in hexadecimal: ***297E***
 
> [!TIP]
> [Binary Calculator](https://www.calculator.net/binary-calculator.html)
> [Binary to Hex Converter](https://www.rapidtables.com/convert/number/binary-to-hex.html)
