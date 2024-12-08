# Description
Can you make sense of this file? Download the file [here](https://artifacts.picoctf.net/c/475/enc_flag).

# Solution
- Check the file contents -> it seems to be like base64 encoded
- Decode it using cyberchef or any decoder tool -> the decoded text still looks like it is base64 encoded
- Keep decoding until flag is found 
- Flag -> `picoCTF{base64_n3st3d_dic0d!n8_d0wnl04d3d_<some_id>}`