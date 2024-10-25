# Description

_#Easy_<br>
_#General_Skills_<br>
_#picoCTF_2024_<br>
_#browser_webshell_solvable_<br>

Know of ***little and big endian***?

[Challenge](endianness.c)

## Solution

> [!NOTE]
> Endianness refers to the order in which bytes within a word or digital data are transmitted over. **Little-endian** is the order in which the little end, meaning that the **least significant** at first sequence. **Big-endian** is the order in which the big end, meaning that the **most significant** at first sequence. 

Example word: gocmw

- To find little-endian
   1. Convert each character to hexadecimal (ASCII).
      
      | Character  | Hex (ASCII) | 
      | ---------- |:-----------:|
      |      g     |     0x67    |
      |      o     |     0x6F    |
      |      c     |     0x63    |
      |      m     |     0x6D    |
      |      w     |     0x77    |

  2. The order would be : 77(w) 6D(m) 63(c) 6F(o) 67(g)
  3. Answer is **776D636F67**
     
- To find big-endian
   1. Convert each character to hexadecimal (ASCII).
      
      | Character  | Hex (ASCII) | 
      | ---------- |:-----------:|
      |      g     |     0x67    |
      |      o     |     0x6F    |
      |      c     |     0x63    |
      |      m     |     0x6D    |
      |      w     |     0x77    |

  2. The order would be : 67(g) 6F(o) 63(c) 6D(m) 77(w)
  3. Answer is **676F636D77**

----------------------------------------------------------------------------------------------------------------------------

Example word: ozoak

- To find little-endian
   1. Convert each character to hexadecimal (ASCII).
      
      | Character  | Hex (ASCII) | 
      | ---------- |:-----------:|
      |      o     |     0x6F    |
      |      z     |     0x7A    |
      |      o     |     0x6F    |
      |      a     |     0x61    |
      |      k     |     0x6B    |

  2. The order would be : 6B(k) 61(a) 6F(o) 7A(z) 6F(o)
  3. Answer is **6B616F7A6F**
     
- To find big-endian
   1. Convert each character to hexadecimal (ASCII).
      
      | Character  | Hex (ASCII) | 
      | ---------- |:-----------:|
      |      o     |     0x6F    |
      |      z     |     0x7A    |
      |      o     |     0x6F    |
      |      a     |     0x61    |
      |      k     |     0x6B    |

  2. The order would be : 6F(o) 7A(z) 6F(o) 61(a) 6B(k)
  3. Answer is **6F7A6F616B**
 
> [!TIP]
> ![image](https://github.com/user-attachments/assets/479b3ce5-650d-405a-9a95-05558ccb02f2)
