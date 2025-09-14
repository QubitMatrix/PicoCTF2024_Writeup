# Description
Can you abuse the banner?

Additional details will be available after launching your challenge instance.

# Solution
- On launching the instance two ports are opened. The first port is shown as a server that is leaking information, trying to connect to that port using netcat will show a password `My_Passw@rd_@1234`
- Connect to the next port using netcat to check its contents
- The first question is the password -> give the password retrieved from the previous step
- Next question is about the top cyber security conference in the world -> DEF CON
- Next is about the first hacker known for phreaking -> John Draper
- The shell is spawned and we can traverse through the filesystem looking for hints -> ls in home directory reveal the banner and text files
- Look for any useful file in the other directories -> /root has a flag.txt and script.py file however it doesn't give the permission to view the flag.txt file
- On carefully analyzing the script.py file it can be noticed that this is the file that was executed before we got the spawned shell. This script opens the banner file in the home directory and prints its content
- This is where symlinks come in -> a symbolic link can be used to link one file to another file symbolically such that it can be accessed using the link
- `ln -s /root/flag.txt banner` -> this will create a symbolic link to access flag.txt through the banner file hence executing the script again will open the flag.txt file
	> Before creating a symlink the file should be deleted `rm banner`
- Quit from the current shell and connect to the server again, this time instead of the initial welcome banner the flag is displayed
- Flag -> picoCTF{b4nn3r_gr4bb1n9_su((3sfu11y_<some_id>}

> The reason that it is not possible to directly read the flag.txt but is possible to read through the link is because a root user is executing the script when the netcat connection is made. This can be confirmed by `ps aux | grep python` where it shows python3 run by root user.
