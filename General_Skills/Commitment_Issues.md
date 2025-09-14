# Description 
I accidentally wrote the flag down. Good thing I deleted it!
Hint: Version Control

# Solution
- `git log` -> shows that some information has been removed in the latest commit, so we can undo this commit and check the difference between the current file and the file that was stage before committing.
1. Option 1
  - `git reset HEAD~1` -> resets latest commit 
  - `git diff` -> the flag is shown as deleted line in current file
2. Option 2
  - `git checkout <commit-hash>` -> commit hash before info was removed
  - `cat message.txt`
- Flag -> picoCTF{s@n1t1z3_<some_id>}
