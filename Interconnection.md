# Interconnection Model #

Currently, MacSim provides three interconnection models.

  1. Very simple latency model
  1. Detailed pipelined router microarchitecture (**Default**)
  1. IRIS interconnection model (Prof. Yalamanchili's group in Georgia Tech)

# How to use simple latency model #

  1. Specify flags
```
./macsim --enable_new_noc=0 --enable_iris=0
```
```
// params.in
enable_new_noc 0
enable_iris 0
```

# How to use detail latency model #

This is the default configuration.

  * Topology
    1. Bi-directional ring
```
noc_topology ring
noc_dimension 1
```
    1. 2D Mesh
```
noc_topology mesh
noc_dimension 2
```

# How to use IRIS #

  1. Specify IRIS option during build process.
```
./build.py --iris
```
```
// macsim.config
[Library]
...
iris: 1
...
```
  1. Enable IRIS flag
```
./macsim --enable_iris=1
```
```
// params.in
enable_iris 1
```