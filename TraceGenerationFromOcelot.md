# Introduction #

GPUOcelot provides many applications from different suites (CUDA SDK, Rodinia, Parboil).

To generate traces from these benchmarks, you can simply need to change the SConscript file in the suite directory.


# Example #

You have to modify/add the following in the $GPUOcelot/test/cuda4.1sdk/SConscript.

Find the line of
```
LIBS=additionalLibs + ['-lglut', '-locelot', libsdk, '-lGLEW', '-lGLU']) 
```
and replace it with
```
LIBS=additionalLibs + ['-lglut', '-locelot', libsdk, '-lGLEW', '-lGLU', '-locelotTrace', '-lz', '-lboost_thread-mt', '-lboost_serialization-mt', '-lboost_wserialization-mt', '-lboost_filesystem-mt', '-lboost_system-mt'])
```


Then, you just need to build the entire suite and run it.

  1. Note that binaries are usually located in .release\_build directory. You need to find it from the directory.
  1. You need to copy (or create symbolic link) data directory to the .release\_build directory.