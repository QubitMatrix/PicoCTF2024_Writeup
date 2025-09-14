# Description
Using a Secure Shell (SSH) is going to be pretty important. Can you ssh as ctf-player to titan.picoctf.net at port 55352 to get the flag? You'll also need the password 83dcefb7. If asked, accept the fingerprint with yes.

[https://linux.die.net/man/1/ssh](https://linux.die.net/man/1/ssh)

# Solution
- To choose custom port -p can be used
- `ssh ctf-player@titan.picoctf.net -p 55352`
- Flag -> picoCTF{s3cur3_c0nn3ct10n_<some_id>}