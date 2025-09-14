# Description
Sometimes you need to handle process data outside of a file. Can you find a way to keep the output from this program and search for the flag? Connect to `jupiter.challenges.picoctf.org 7480`.

# Solution
- Connecting to the server using netcat shows a lot of messages hinting that the flag is hidden in those messages
- We can do a netcat connection and send it to grep to find the flag
- `nc jupiter.challenges.picoctf.org 7480 | grep -i "picoctf"`
- Flag -> `picoCTF{digital_plumb3r_<some_id>}`