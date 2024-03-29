# Description 
My team has been working very hard on new features for our flag printing program! I wonder how they'll work together?

# Solution 
- The question hints at team work which means it has to be related to merge conflicts
- First we check the content of the file. It is the starting part of the print statement for printing the flag.
- `git branch -a` -> shows all branches, there are 3 features each in a branch
- `git merge feature/part-1` -> there is no merge conflict and the code is updated to display first part of the flag
- `git merge feature/part-2` -> has merge conflicts that cannot be automatically resolved, to resolve conflicts simple vi editor can be used
	- Lines with conflicts are prefixed with special markers like `<<<<<<<`, `=======`, and `>>>>>>>`.
    - `<<<<<<<`: Denotes the beginning of your local changes.
    - `=======`: Separates the base version.
    - `>>>>>>>`: Denotes the beginning of the remote branch changes.
- Remove all the special markers and commit the changes and repeat the process for feature 3.
- `python3 flag.py` will give the complete flag

Conflicting code for feature 2 merge:
```
print("Printing the flag...")
<<<<<<< HEAD
print("picoCTF{t3@mw0rk_", end='')
=======

print("m@k3s_th3_dr3@m_", end='')
>>>>>>> feature/part-2
```

Conflicting code for feature 3 merge:
```
print("Printing the flag...")
<<<<<<< HEAD
print("picoCTF{t3@mw0rk_", end='')
print("m@k3s_th3_dr3@m_", end='')
=======

print("w0rk_e4b79efb}")
>>>>>>> feature/part-3
```

Flag -> picoCTF{t3@mw0rk_m@k3s_th3_dr3@m_w0rk_<some_id>}