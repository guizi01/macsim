# Introduction #

MacSim supports x86-ISA simulations. Although both single-threaded/multi-threaded applications are _runnable_, but the correct execution for multi-threaded applications are not guaranteed due to the lack of cache coherence protocol in MacSim.

We use PIN [http://www.pintool.org], a binary instrumentation tool, as a frontend emulator. We provide a pintool, called x86 trace generator, in MacSim repository (macsim\_repo/tools/x86\_trace\_generator).

Please note that our trace generator may not be backward/forward compatible with different PIN versions.
Currently, PIN **56759** revision (Jan 20, 2013) must be used. For older versions of macsim, please try to use PIN **41150** revision (June 07, 2011).


# How to build the trace generator #

  1. Download PIN
  1. Modify makefile of trace\_generator to set up pintool path
    * search PIN\_HOME, PIN\_ROOT, and PIN\_KIT
    * modify these according to your PIN path
  1. Build trace generator
```
make
```


# How to generator a trace #

  * Assume you have a binary 'BIN' and a command to run 'BIN' is 'BIN arg1 arg2'
  * Assume pin binary is available or you need to use appropriate path (Usually, pin binary path is in **$PINTOOL/pin**
  * Execute x86 trace generator with PIN
```
pin -t ./obj-intel64/x86_generator.so -- BIN arg1 arg2
```


# Other options #

  * -trace : trace name
  * -skip : how many instructions to skip until the beginning of the trace generation
  * -max : maximum number of instructions to generate
  * -thread : number of threads to run

# Outcome #

```
trace.txt // trace information file
trace_0.raw // gzipped trace file for thread 0
```