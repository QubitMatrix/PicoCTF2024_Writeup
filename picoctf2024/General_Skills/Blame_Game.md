# Description 
Someone's commits seems to be preventing the program from working. Who is it?

# Solution
- Check the file content first with `cat message.py` -> notice the syntax is wrong and that is change to look out for
- `git log <filename>` -> can be used to get only logs which are involved with the given file
- `git log message.py` -> shows two commits and the first commit is trying to optimize the code and has introduced the bug, the author name for this commit has the flag
- Flag -> picoCTF{@sk_th3_1nt3rn_<some_id>}