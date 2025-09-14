# Description
Can you crack the password to get the flag? Download the password checker [here](https://artifacts.picoctf.net/c/12/level1.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/12/level1.flag.txt.enc) in the same directory too.

# Solution
- Once the files downloaded and the python script is run we see that a password is required.
- On checking the source code we see that the if statement has the required password - 8713
- Execute the code with the password to get the flag
- Flag -> `picoCTF{545h_r1ng1ng_<some_id>}`