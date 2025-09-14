# Description
The Network Operations Center (NOC) of your local institution picked up a suspicious file, they're getting conflicting information on what type of file it is. They've brought you in as an external expert to examine the file. Can you extract all the information from this strange file?   
Download the suspicious file [here](https://artifacts.picoctf.net/c_titan/7/flag2of2-final.pdf).

# Solution
- since the question hints at unknown file type first try `file` on the pdf file
- It is named as pdf but file command shows that it is a png
- Open the pdf, it contains the second half of the flag
- Convert the pdf into a png using `mv flag2of2-final.pdf a.png`
- Open the png file, the first half of the flag is shown
- Flag -> `picoCTF{f1u3n71n_pn9_&_pdf_<some_id>}`