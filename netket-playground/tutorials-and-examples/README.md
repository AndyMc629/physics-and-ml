## Examples
Taken from https://github.com/netket/netket/blob/master/Tutorials

## Issues
Had some issues running this due to the open MPI I had installed breaking.

Steps:

1. Run  
```bash
$ apt-cache search MPI | grep -w MPI| awk '{print $1}' | xargs dpkg -l 2>/dev/null
```
to see what MPI packages you have installed.
2. Then went through each library and ran (actually only needed to run one):
```bash
$ sudo apt remove LIBRARY
$ sudo apt autoremove LIBRARY
```
3. Donwload the openmpi source, change to the openmpi installation directory and run
```bash
$ ./configure --prefix=/usr/local --disable-dlopen
```
4. Run 
```bash
$ make all install 
```
... this takes a while 
