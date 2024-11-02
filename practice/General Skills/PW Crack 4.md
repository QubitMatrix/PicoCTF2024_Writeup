# Description
Can you crack the password to get the flag?   
Download the password checker [here](https://artifacts.picoctf.net/c/19/level4.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/19/level4.flag.txt.enc) and the [hash](https://artifacts.picoctf.net/c/19/level4.hash.bin) in the same directory too.   
There are 100 potential passwords with 1 being correct. You can find these by examining the password checker script.

# Solution
- The source code has 100 values in a list 
- Trying these values one by one will give the answer for the last word
	- To automate the process we iterate the values in the list and call the function with that value and comment out the input line
- Flag -> `picoCTF{fl45h_5pr1ng1ng_<some_id>}`