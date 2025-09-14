# Description
Don't power users get tired of making spelling mistakes in the shell? Not anymore! Enter Special, the Spell Checked Interface for Affecting Linux. Now, every word is properly spelled and capitalized... automatically and behind-the-scenes! Be the first to test Special in beta, and feel free to tell us all about how Special streamlines every development process that you face. When your co-workers see your amazing shell interface, just tell them: That's Special (TM)

# Solution
- When we try any command we can see that the spelling is getting altered and first alphabet is capitalized so we are not able to run any commands
- A special feature of shell is parameter expansion -> `${}`
- `${parameter}` can be used to substitute the value of parameter
	- This syntax can be used to run our commands
	- ${command=ls} can be used to get the output of running just ls -> this works by setting the value to the parameter named command and then using that value
	- The word command can be replaced by any parameter which is not part of the shell variables that exist already -> using existing variables will only retrieve existing value and will not set it to new value
- `${command=ls}` -> `${command=ls blargh}` -> `${command=cat ./blargh/flag.txt}`
- Flag -> `picoCTF{5p311ch3ck_15_7h3_w0r57_<some_id>}`