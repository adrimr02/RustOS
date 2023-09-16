# RustOS
This is a project following [@phil-opp](https://github.com/phil-opp/blog_os) blog on how to build an operating system in Rust.

## How to run
- Clone the repository with
  ```
  git clone https://github.com/adrimr02/RustOS.git
  ```
- Install [Rust](https://www.rust-lang.org/)
- Switch to the Nightly version of Rust with
  ```
  rustup override set nightly
  ```
- Install Cargo needed dependencies and tools
  ```
  rustup component add rust-src
  cargo install bootimage
  rustup component add llvm-tools-preview
  ```
- Download and install [QEMU](https://www.qemu.org/) as a virtualizer to run the OS (You might need to add QEMU to your PATH variable if you're using Windows)
- Compile the OS
  ```
  cargo bootimage
  ```
- Run it with QEMU (terminal must be in the root folder of the project)
  On Unix systems
  ```
  qemu-system-x86_64 -drive format=raw,file=target/x86_64-rust_os/debug/bootimage-rust_os.bin
  ```
  On Windows
  ```
  qemu-system-x86_64 -drive format=raw,file=target\x86_64-rust_os\debug\bootimage-rust_os.bin
  ```
- You can skip the last two steps with
  ```
  cargo run
  ```
## Credits
- [Original Blog](https://os.phil-opp.com/)
- [Philipp's profile](https://github.com/phil-opp)
