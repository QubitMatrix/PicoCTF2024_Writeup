# Description
Can you crack the password to get the flag?   
Download the password checker [here](https://artifacts.picoctf.net/c/31/level5.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/31/level5.flag.txt.enc) and the [hash](https://artifacts.picoctf.net/c/31/level5.hash.bin) in the same directory too. Here's a [dictionary](https://artifacts.picoctf.net/c/31/dictionary.txt) with all possible passwords based on the password conventions we've seen so far.

# Solution
- The source code has 65536 values in a file
- Trying these values one by one will give the answer for the last word
	- To automate the process we read the file and store the values in a list. Next iterate the values in the list and call the function with that value and comment out the input line
- Flag -> `picoCTF{h45h_sl1ng1ng_<some_id>}
`