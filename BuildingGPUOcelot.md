The following commands should build **gpuocelot library** and **trace generators** without **any errors** (tested with gpuocelot [r2097](https://code.google.com/p/macsim/source/detail?r=2097)), except for the errors due to warnings such as:
  1. **variable ## set but not used** =>  please fix them appropriately.
  1. **will be initialized after [-Werror=reorder]** => please move **uint64\_t total\_inst\_count;** below **int kernel\_count;** in the interface/X86TraceGenerator.h.

(or, you can use sudo ./build.py --no-werr --install)

Please visit http://code.google.com/p/gpuocelot/ for details.

```
$ svn checkout http://gpuocelot.googlecode.com/svn/trunk/ gpuocelot
$ cd gpuocelot/ocelot
$ sudo ./build.py --install                
$ cd ../trace-generators
$ libtoolize; aclocal; automake; autoconf; ./configure
$ make; sudo make install
```