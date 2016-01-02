# Different memory types #

  * l3\_coupled\_network
  * l3\_decoupled\_network
  * no\_cache: all cache hierarchies are disabled.
  * l2\_coupled\_local
  * l2\_decoupled\_network
  * l2\_decoupled\_local


# How to set up different memory type #

  1. Change the default value in macsim/def/memory.param.def
```
param<MEMORY_TYPE, memory_type, string, TYPE>
```
  1. params.in
```
memory_type TYPE
```
  1. command line
```
./macsim --memory_type=TYPE
```