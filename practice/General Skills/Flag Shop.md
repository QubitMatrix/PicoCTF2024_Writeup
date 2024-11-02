# Description
There's a flag shop selling stuff, can you buy a flag? [Source](https://jupiter.challenges.picoctf.org/static/dd28f0987f28c894f35d5d48564c3402/store.c). Connect with `nc jupiter.challenges.picoctf.org 44566`.

# Solution
- Analyzing the code it can be seen that integer overflow vulnerability can be exploited to reveal the flag
- To do so we need to subtract enough from the initial limit 1100 such that it wraps around
	- the number of flags we choose multiplied by 9 will be subtracted from 1100 this we will need 1100 + 2147483648 to cause wraparound 
	- the number of flags required will be ceil of 2147482547/900
- Flag -> `picoCTF{m0n3y_bag5_<some_id>}`