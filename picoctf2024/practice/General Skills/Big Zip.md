# Description
Unzip this archive and find the flag.
- [Download zip file](https://artifacts.picoctf.net/c/505/big-zip-files.zip)

# Solution
- First we can unzip the file using `unzip`
- We can try searching for any file with flag in the name using `find ./big-zip-files -name "*flag*"` => but this doesn't show any output meaning that there is no such file
- Next we search for the flag directly using grep -> `grep -i -r "picoctf" ./big-zip-files` => the flag is revealed 
- Flag -> `picoCTF{gr3p_15_m4g1c_<some_id>}`