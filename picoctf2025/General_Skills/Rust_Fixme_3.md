# Description
Have you heard of Rust? Fix the syntax errors in this Rust file to print the flag! Download the Rust code [here](https://challenge-files.picoctf.net/c_verbal_sleep/dcdaf491b35c1d0f5075e9583edbbb7aaea1dffb6ad32bc000e4d87b5200ff7b/fixme3.tar.gz). 

https://doc.rust-lang.org/book/ch20-01-unsafe-rust.html

# Solution
- `tar -xf fixme.tar.gz` - to unzip the archive
- `cargo build` - shows that there is unsafe call and requires an unsafe block
- Errors in the program
	- Enclose the unsafe block within the `unsafe{}` block in it
- `cargo run` will run the rust program
- Flag -> picoCTF{n0w_y0uv3_f1x3d_1h3m_411}