# Description 
How about some hide and seek?   
Download this file [here](https://artifacts.picoctf.net/c_titan/4/unknown.zip)

# Solution
- Extracting the zip gives a jpg image
- Check for details through `file` and `strings` but it does not give anything useful
- Try exiftool to search for any hints -> the attribution url looks like a base64 value so let's try decoding that value
- `echo "base64 value from previous step" | base64 -d`
- Flag -> picoCTF{ME74D47A_HIDD3N_<some_id>}