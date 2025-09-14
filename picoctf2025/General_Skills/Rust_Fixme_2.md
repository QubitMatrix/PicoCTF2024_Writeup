# Description
The Rust saga continues? I ask you, can I borrow that, pleeeeeaaaasseeeee? Download the Rust code [here](https://challenge-files.picoctf.net/c_verbal_sleep/babfbee79718a6363826ba86300173ffde6d81577e9dd07d4130c53a7eecf6c3/fixme2.tar.gz).

https://doc.rust-lang.org/book/ch04-02-references-and-borrowing.html
# Solution
- `tar -xf fixme.tar.gz` - to unzip the archive
- `cargo build` - will show the errors
- `cargo run` will run the rust program
- Errors in the program
	- `borrowed_string: &String` -> `borrowed_string: &mut String` => makes the variable mutable like pass by address
	- `let party_foul` -> `let mu party_foul` => declares it as a changeable variable
	- `decrypt(encrypted_buffer, &party_foul)` -> `decrypt(encrypted_buffer, &mut party_foul)` => passes it as a changeable value
- Flag -> picoCTF{4r3_y0u_h4v1n5_fun_y31?}