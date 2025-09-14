# Description
People keep trying to trick my players with imitation flags. I want to make sure they get the real thing! I'm going to provide the SHA-256 hash and a decrypt script to help you know that my flags are legitimate.   
You can download the challenge files here:   
[challenge.zip](https://artifacts.picoctf.net/c_rhea/10/challenge.zip)

Additional details will be available after launching your challenge instance.

# Solution
- on inspecting the decrypt.sh file it is noticed that the path is an absolute path and will not be matched unless it was downloaded in the home directory under the name of ctf-player as the hostname -> change the path to relative path `./files/$file_name` 
- `openssl enc -d -aes-256-cbc -pbkdf2 -iter 100000 -salt -in "./files/$file_name" -k picoCTF` -> decrypts the given file using aes cbc mode and a password based key decryption function with 100000 iterations and random salt with input file ./files/$file_name and check for picoCTF
- on running the shell script with a file from files folder gives an output that it is fake flag. This process can be repeated for all the files in the files folder to find the actual flag
- Can be automated as follows
	- Create a script to call decrypt.sh for every file in files
		run.sh:   
		``` 
		while read line
		do
	        bash decrypt.sh $line
	        echo $line
		done < "list.txt"
		```
	- Get the list of all files and store it in list.txt   
		`cd files && ls > ../list.txt && cd ../`
	- Execute run script and grep for picoCTF  
		`bash run.sh | grep picoCTF`
- Flag ->  picoCTF{trust_but_verify_<some_id>}