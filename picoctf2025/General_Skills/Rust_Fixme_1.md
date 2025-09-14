# Description
Have you heard of Rust? Fix the syntax errors in this Rust file to print the flag! Download the Rust code [here](https://challenge-files.picoctf.net/c_verbal_sleep/3f0e13f541928f420d9c8c96b06d4dbf7b2fa18b15adbd457108e8c80a1f5883/fixme1.tar.gz).   

https://doc.rust-lang.org/book/ch01-03-hello-cargo.html
# Solution
- `tar -xf fixme.tar.gz` - to unzip the archive
- `sudo apt install cargo` - install the rust package manager
- Dependencies are mentioned in `Cargo.toml` and it can be built using `cargo build`
- `cargo run` will run the rust program
- Errors in the program
	- Semicolon missing
	- Replace ret with `return ()` keyword
	- Print statement needs formatting specifiers - `:?` to `{:?}`
- Flag -> picoCTF{4r3_y0u_4_ru$t4c30n_n0w?}