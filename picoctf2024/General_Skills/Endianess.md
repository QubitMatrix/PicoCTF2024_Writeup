# Description
Know of little and big endian?   
https://levelup.gitconnected.com/little-endian-and-big-endian-74ab6441b2a7
# Solution
- This question can be solved in two ways
	- Check ASCII table
		- find the **hex** equivalent for each of the character in the given word
		- for little endian the least significant byte is stored in the lower address, read the word right to left and find the ascii value of each letter
		- for big endian the most significant byte is stored at the lower address, read the word left to right and find the ascii value of each letter.
	- Run the source code which is provided
		- changing the challenge word from random generated word to the given word and run it locally to get the expected answer and paste this answer in the netcat connection
- Flag -> picoCTF{3ndi4n_sw4p_su33ess_<some_id>}