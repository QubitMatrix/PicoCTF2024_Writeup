# Description
Here's a file that was recovered from a 32-bits system that organized the bytes a weird way. We're not even sure what type of file it is.   
Download it [here](https://artifacts.picoctf.net/c_titan/35/challengefile) and see what you can get out of it

# Solution
- Check what type of file it is using `file challengefile` -> just gives data
- Use `xxd challengefile` to check the hex value -> it can be seen that the first 4 bytes are the reverse of the jpg header `FF D8 FF E0`
- Every 4 bytes have to be reversed to get the correct file
- Script to automate the process
	end1.py
	```
	with open('challengefile','rb') as f:
		hex_data=f.read()
		file_hex=hex_data.hex()
	
	array_data=[file_hex[i:i+8] for i in range(0,len(file_hex),8)]
	reversed_hex_strings=[]
	for hex_string in array_data:
		reversed_hex_string = ''.join(reversed([hex_string[i:i+2] for i in range(0, len(hex_string), 2)]))
		reversed_hex_strings.append(reversed_hex_string)
	with open('reversedHex.txt', 'w') as f:
		for reversed_hex_string in reversed_hex_strings:
			f.write(reversed_hex_string)
	 ```
- The value in reversedHex.txt can be copied into an online hex to image convertor to get the image which shows the flag 
- Flag -> picoCTF{cert!f1Ed_iNd!4n_s0rrY_3nDian_<some_id>}