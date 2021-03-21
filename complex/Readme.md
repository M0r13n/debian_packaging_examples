# Compile and Package grep from source
This script fetches a version of grep from https://ftp.debian.org/debian/pool/main/g/grep via `dget`.
It then installs requires `build-deps` and compiles grep. Finally a `.deb` Package of grep is created.

## Build
Run `./build`