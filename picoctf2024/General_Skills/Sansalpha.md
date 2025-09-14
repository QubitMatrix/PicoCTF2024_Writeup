# Description 
The Multiverse is within your grasp! Unfortunately, the server that contains the secrets of the multiverse is in a universe where keyboards only have numbers and (most) symbols.

Additional details will be available after launching your challenge instance.


# Solution
- The server accepts only numbers and some special characters as input, letters and '\\' are not recognized.
- First let's see what files we are dealing with by using `./*` -> this immediately shows a folder 'blargh'
- Next let's check the contents inside this directory using `./??????/*` -> we find a flag.txt file inside this folder
- We found the file but we need commands like cat or vi to check its content. We can use regex to move through the file system and see the files that can be accessed and executed without using any letters.
- Start with /???/ -> we are able to access the bin folder which has most of the command executables
- Try all possibilities by increasing the number of ? in /???/? -> at /???/?????? we see a base32 executable try to access the base64 executable and ending in an error
	> The reason for this is that the shell expands the regex and takes the first match as the executable and the rest of the match as the arguments to this executable. We can exploit this to view the base64 encoding of our flag.txt file if we can construct the regex to particularly match only /bin/base64
- First lets try /???/????64 so that we don't execute base32 -> `/???/????64 ./??????/*` => this however expands to both /bin/base64 as well as /bin/x86_64 hence the command after expansion would look like this on the server `/bin/base64 /bin/x86_64 ./blargh/flag.txt`. Hence it shows an error that /bin/x86_64 is an extra operand
- To avoid the previous error try to be more specific -> `/???/???[!_]64 ./??????/*` => this expands correctly to be /bin/base64 blargh/flag.txt but still it takes this as an extra operator which could be because of some duplicate files which didn't show up earlier with `??????/*` 
- `/???/???[!_]64 ??????/????????` will finally give the base64 encoding of the flag.txt contents -> use this value to decode and get the flag
- Use a normal shell and execute `echo <base64 value from previous step> | base64 -d` to decode the value
- Flag -> picoCTF{7h15_mu171v3r53_15_m4dn355_<some_id>}