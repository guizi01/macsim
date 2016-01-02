[DRAMSim2](http://www.ece.umd.edu/dramsim/) has been integrated with MacSim for more detailed DRAM simulations.


# How to use DRAMSim2 with MacSim #

Specify a DRAMSim2 option during a build process.
```
./build.py --dramsim
```

Or you can specify it in the macsim.config file
```
[Library]
dram: 1
```

During the build process, DRAMSim2 source code files will be downloaded from DRAMSim2's repository if the directory does not exist.

Then, add below to register\_functions(void) in macsim.cc to register DRAMSim2
```
dram_factory_c::get()->register_class("DRAMSIM", dramsim_controller);
```

# How to choose DRAMSim2 configuration file #

To be added