# Description
Want to play a game? As you use more of the shell, you might be interested in how they work! Binary search is a classic algorithm used to quickly find an item in a sorted list. Can you find the flag? You'll have 1000 possibilities and only 10 guesses. Cyber security often has a huge amount of data to look through - from logs, vulnerability reports, and forensics. Practicing the fundamentals manually might help you in the future when you have to write your own tools! 

You can download the challenge files here:
- [challenge.zip](https://artifacts.picoctf.net/c_atlas/4/challenge.zip)

Additional details will be available after launching your challenge instance.

# Solution
- Since it says binary search and the number is from 1 to 1000 first start with 500. If it says lower then the number should be lower than the guess and if it says higher it should be higher than the guess. Continuing this process using average of the known upper and lower limits at each step will give the answer in less than 10 tries
- Flag -> picoCTF{g00d_gu355_<some_id>}