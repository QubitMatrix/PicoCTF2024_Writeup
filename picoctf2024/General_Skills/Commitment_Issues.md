# Description 
I accidentally wrote the flag down. Good thing I deleted it!
Hint: Version Control

# Solution
- `git log` -> shows that some information has been removed in the latest commit, so we can undo this commit and check the difference between the current file and the file that was stage before committing.
- `git reset HEAD~1` -> resets latest commit 
- `git diff` -> the flag is shown as deleted line in current file
- Flag -> picoCTF{s@n1t1z3_<some_id>}