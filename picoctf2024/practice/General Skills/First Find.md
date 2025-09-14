# Description
Unzip this archive and find the file named 'uber-secret.txt'
- [Download zip file](https://artifacts.picoctf.net/c/500/files.zip)

# Solution
- After unzipping the file we need to search for the path of the given file to be able to view its contents -> `find ./files -name "uber-secret.txt"`
- Once the path is know we can do a `cat <path>` to get the flag
- Flag -> `picoCTF{f1nd_15_f457_<some_id>}`