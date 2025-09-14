# Description
How well can you perfom basic binary operations? Start searching for the flag here `nc titan.picoctf.net 49152`

# Solution
- Python IDLE can be used to solve the binary operations, prefix the two numbers with 0b and perform the operations -> this gives the answers in decimal => use bin(decimal value) to get the binary equivalent and enter only the number without `0b` as the answer
- Final operation requires hexadecimal equivalent -> hex(decimal value) => answer is the result of hex() without `0x`
- Flag -> picoCTF{b1tw^3se_0p3eR@tI0n_<some_id>}