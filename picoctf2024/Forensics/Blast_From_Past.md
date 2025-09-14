# Description
The judge for these pictures is a real fan of antiques. Can you age this photo to the specifications?   
Set the timestamps on this picture to `1970:01:01 00:00:00.001+00:00` with as much precision as possible for each timestamp. In this example, `+00:00` is a timezone adjustment.   
Any timezone is acceptable as long as the time is equivalent. As an example, this timestamp is acceptable as well: `1969:12:31 19:00:00.001-05:00`. For timestamps without a timezone adjustment, put them in GMT time (+00:00).   
The checker program provides the timestamp needed for each.   
Use this [picture](https://artifacts.picoctf.net/c_mimas/73/original.jpg).

Additional details will be available after launching your challenge instance.
# Solution
- Use exiftool to check the details about the file
- exiftool can also be used to change the details about the image using the tags displayed with exiftool
- change the main dates like create date, modify data and date/time original   
	`exiftool -"CreateDate"="1970:01:01 00:00:00.001" original.jpg`   
	`exiftool -"ModifyDate"="1970:01:01 00:00:00.001" original.jpg`   
	`exiftool -"DateTimeOriginal"="1970:01:01 00:00:00.001" original.jpg`   
- Submit the file using the first command and check the results using the second link (if this doesn't work run it without `-d`)
- Only first 3 checks pass and the next one requires changing the attribute `SubSecCreateDate` and the precision required is more than that exiftool can give, so some other tool has to be used for this
- python's pyexif module can be used to change the value with greater precision
- 
```
from pyexif import pyexif   
image_path="./original.jpg"   
metadata=pyexif.ExifEditor(image_path)   
metadata.setTag('SubSecCreateDate','1970:01:01 00:00:00.001');   
metadata.setTag('SubSecModifyDate','1970:01:01 00:00:00.001');   
metadata.setTag('SubSecDateTimeOriginal','1970:01:01 00:00:00.001');   
```
- Now the last test is failing and the timestamp has to be changed, this attribute cannot be found directly in exiftool and if we try to modify it using pyexif 
- `metadata.setTag('Timestamp','1970:01:01 00:00:00.001');` -> this changes the timestamp for XMP-apple-fi by default but the server is checking for Samsung, moreover it requires the value to be integer which means we have to give it the time in unix format
- `exiftool -v3 original.jpg` -> gives more verbose details about the file -> the timestamp under samsung can be found in this and it can be noticed the time is in unix format and the address of this attribute is also given which can be used to modify its value   
	![Exiftool](https://github.com/QubitMatrix/QubitMatrix/assets/60323193/07f225d5-5965-410e-b6e0-93b779328a54)
- We need to modify the jpg file contents directly to be able to modify this field 
	- use a hex editor like hexedit
	- go to the address of timestamp -> CTRL+J to search for specific address
	- modify the current unix time to epoch 1 (replace all numbers with 30 which is equivalent to 0 except the last digit which should be 31)   
		![Hexedit](https://github.com/QubitMatrix/QubitMatrix/assets/60323193/d59ad536-56ce-4e27-b400-5b4b680e0581)
	- CTRL+X and yes to save
- Submit the file and check again
- Flag -> picoCTF{71m3_7r4v311ng_p1c7ur3_<some_id>}
