# Description
Can you crack the password to get the flag? Download the password checker [here](https://artifacts.picoctf.net/c/14/level2.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/14/level2.flag.txt.enc) in the same directory too.

# Solution
- Once the files downloaded and the python script is run we see that a password is required.
- On checking the source code we see that the if statement has the required password in terms of chr -> decode the password by pasting the RHS of the condition in python to get the password - 4ec9
- Execute the code with the password to get the flag
- Flag -> `picoCTF{tr45h_51ng1ng_<some_id>}`