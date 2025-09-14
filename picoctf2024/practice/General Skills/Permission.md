# Description
Can you read files in the root file?   
The system admin has provisioned an account for you on the main server   
Can you login and read the root file?

# Solution
- The task is to read the root file so we first navigate to the '/' directory to see the contents -> as expected there is a root directory, so we try navigating inside this but we cannot as it requires privileged access
- First check what are the elevated permissions on the given account 
	- `whoami` gives which user account is being used
	- `sudo -l` will give a list of sudo privileged actions => it is seen vi have escalated privileges
- Vim is a text editor but has features beyond traditional text editors -> one main feature that we can exploit is the fact that it is possible to run shell commands withing vim
	- `sudo vim`
	- This can be done by prefixing the command with `!`
	- As our goal was to go into the root directory -> `! cd root` within vim will go into the root directory and we can read the list of files using `! ls root`
	- Initially this shows no files but it is possible that it might be hidden files so we try `ls -la root` and we see a few files which includes a flag file
	- Now to read it we can use `! cd root && cat .flag.txt`
- Flag -> `picoCTF{uS1ng_v1m_3dit0r_<some_id>}`

> We can also just open a shell first and run all the commands through the shell -> `! /bin/bash` inside vim would open a shell and on running a `whoami` we can see the shell has root privilege 