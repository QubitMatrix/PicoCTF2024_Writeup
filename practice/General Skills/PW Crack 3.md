# Description
Can you crack the password to get the flag?   
Download the password checker [here](https://artifacts.picoctf.net/c/16/level3.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/16/level3.flag.txt.enc) and the [hash](https://artifacts.picoctf.net/c/16/level3.hash.bin) in the same directory too.   
There are 7 potential passwords with 1 being correct. You can find these by examining the password checker script.

# Solution
- The source code has seven values in a list 
- Trying these values one by one will give the answer for the last word
- Flag -> `picoCTF{m45h_fl1ng1ng_<some_id>0}`