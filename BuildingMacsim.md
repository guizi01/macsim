# How to build macsim #

Currently, MacSim support only SCons build process.
Note that we will keep automake process only for the macsim-sst build, which is described in this [page](http://code.google.com/p/macsim/wiki/BuildingMacsimSST).

## Requirement ##
  1. Compiler
    * c++0x support
    * We tested g++ and icc compilers. However, icc compiler may not work with external libraries.
  1. scons
    * ubuntu
```
apt-get install scons
```

## Build Steps ##

```
./build.py
```

  * build options
    * -j (--thread) : specify number of threads for parallel build
    * -d : debug build (-g)
    * -p : gprof build (-pg)
    * -c : clean
    * -t : build test
    * --dramsim : using DRAMSim2
    * --power : power model (with EnergyIntrospector)
    * --iris : Iris interconnection model

  * Note that you can choose either opt (default), dbg, or gpf build, not multiple.

  * However, you can choose any combination of libraries you want (DRAMSim2, EI, Iris).

## Configuration file ##

MacSim provides a top-level configuration file called **macsim.config**. The sample content of the configuration file is as following:

```
## MacSim Configuration File

[Build]
debug: 0
gprof: 0

[Library]
dram:  0
power: 0
iris:  0
```

Although you can specify these options in the command lines with **build.py**, specifying in this file would make your build process easier.