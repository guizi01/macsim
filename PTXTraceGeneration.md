# Introduction #

This page describes how to generate GPU (PTX) traces using GPUOcelot


# Build GPUOcelot libraries #

Please refer to http://code.google.com/p/gpuocelot/ to install GPUOcelot




# Building a binary with GPUOcelot libraries #
  * Link against GPUOcelot libraries by adding following flags.
```
`OcelotConfig -l` -locelotTrace
```
  * Sometimes you many need to include boost libraries as well.
```
-lboost_thread-mt -lboost_serialization-mt -lboost_wserialization-mt -lboost_filesystem-mt -lboost_system-mt
```


# Copy GPUOcelot configuration file #

  1. Copy configure.ocelot file from GPUOcelot.
  1. Edit the following line in **trace:** section.
```
x86Trace: true
```
  * This is the sample configure.ocelot file content.
```
{
    ocelot: "ocelot",
    trace: {
        database: "traces/database.trace",
        ...
        x86Trace: true 
    },
    cuda: {
        implementation: CudaRuntime,
        runtimeApiTrace: "trace/CudaAPI.trace"
    },
    executive: {
        devices: [ emulated ],
        port: 2011,
        host: "127.0.0.1",
        optimizationLevel: none,
        workerThreadLimit: 2,
        warpSize: 4
    },
    optimizations: {
        subkernelSize: 1
    }
}
```


# Generating a trace #

Once you have your binary linked against GPUOcelot libraries,

  1. You need to create a kernel information file.
  1. You need to setup env. variable for GPUOcelot trace generator.

  * Although you can follow steps below, we provide a script file to do so. Please find $(macsim\_repo)/trunk/tools/gpu\_tracegen.py for more descriptions.


## How to get kernel information ##

  1. Execute the following command for all cuda files.
```
nvcc --cubin --ptxas-options=-v -arch sm_20 *.cu
```
  1. You will get following information.
```
ptxas info    : Compiling entry function '_Z7cenergyifPf' for 'sm_20'
ptxas info    : Used 26 registers, 48 bytes cmem[0], 64000 bytes cmem[2], 12 bytes cmem[16]
```
  1. Write a file with following convention.
```
kernel_name register_usage shared_memory_usage
```
    * For example
```
_Z7cenergyifPf 26 0
```


## Setting env. variables ##

GPUOcelot trace generator requires following information that is set with environmental variables.

```
export TRACE_PATH=trace_path_that_you_want_to_store
export USE_KERNEL_NAME=1
export KERNEL_INFO_PATH=kernel_information_file_that_you_created
export COMPUTE_VERSION=2.0
```