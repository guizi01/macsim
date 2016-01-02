# MacSim Clock Domain #

MacSim has 5 different clock domains: CPU cores, GPU cores, L3 cache tiles, Interconnection, and Memory controllers.


# How to setup clock #

There are 5 corresponding knob parameters.
```
clock_cpu
clock_gpu
clock_l3
clock_noc
clock_mc
```

The value can be integer or float (in GHz). All float numbers will be rounded to one decimal place. Therefore, 1.443 GHz will be treated as 1.4 GHz.


# Tips #

  1. If you are running CPU-only or GPU-only simulations, please set clock\_cpu and clock\_gpu to same values.