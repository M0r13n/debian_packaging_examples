# How to create Debian packages examples

- [Auto](/auto)
    * an example that uses `debuild` to create a debian package
    * includes a Makefile that compiles a  simple hello world program in C

- [Complex](/complex)
    * an example that uses fetches `grep` sources
    * compiles grep and then creates a debian package via `dpkg-buildpackage`

- [Simple](/simple)
    * an simple exmaple that creates a Debian package completly by hand
    * packages a simple shell script into a `.deb` file


# Debian Packaging

## What is a Debian Package?
- collection of files that form a application or library
- consistent manner of automated installs, upgrade, configures and removes of a computer program
- each Debian package consists of two components: `source package` and `binary package`
- 
- **Source Package**: 
	- `.dsc` file
	- provides all of the necessary files to compile or otherwise, build the desired piece of software.
	- upstream sources are bundles in a tarball
	- a description contains important metadata (name, dependencies, etc)
	- 
- **Binary PAckage**: 
	- `.deb` file
	- contains a ready to run program
	- knows how to add itself, remote itself and even configure itself
	- actually gets distributed and installed.


- A `.deb` can be manually constructed and can come without a source package


### Naming
- Debian Standard Naming Schema:
- `<project>_<major version>.<minor version>-<package revision>`
- only `lowercase alphanums` + `+ -` names are allowed
- `hello-debian` or `helloworld` would be okay
- `hello_debian` or `Foo/bar` are not okay




## Structure of a binary Debian package (.deb)

- binaries and resources should be placed in the same way, as they should be installed on a target system:
	- if the folder contains a `/usr/local/bin/some_exe` file
    - a executable `some_exe` would be installed into `/usr/local/bin`

- `DEBIAN` folder
    - this folder is used to hold special files, containing metadata
    - these files tell your package manager how it should install your app

- is an ar archive: `ar tv ./wget_1.12-2_amd64.deb`
- quality check via `lintian` -> `lintian ./wget_1.12-2_amd64.deb`

