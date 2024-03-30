# Description
If you can find the flag on this disk image, we can close the case for good!   
Download the disk image [here](https://artifacts.picoctf.net/c_titan/63/disk.flag.img.gz).   

# Solution
- The file is a compressed zip image -> `gzip -d disk.flag.img.gz` to get the image
- Analyze the image using autopsy tool -> after creating a case and importing the disk image search using keyword search and choose ascii -> search for .txt files and that gives a bunch of files
- Analyze each file and there is a file which has `pic` as part of its data this is where the flag starts, all consequent files have three characters of the flag until `}` is found in one of the files
- Flag -> picoCTF{1_533_n4m35_<some_id>}