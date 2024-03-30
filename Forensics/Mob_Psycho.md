# Description
Can you handle APKs?   
Download the android apk [here](https://artifacts.picoctf.net/c_titan/51/mobpsycho.apk).

# Solution
- Try to check for anything with the flag format in the files -> `unzip -l mobpsycho.apk | grep picoCTF` => (list contents without extracting)
- Next try searching for any file with flag in the name -> `unzip -l mobpsycho.apk | grep flag` => this shows the path of the flag.txt file
- Extract the apk using unzip and traverse to the flag.txt file and print its contents -> this gives a random set of numbers 
- Give this number as input to cyberchef under magic mode and it gives the flag when it tries using hex conversion
- Flag -> picoCTF{ax8mC0RU6ve_NX85l4ax8mCl_<some_id>}