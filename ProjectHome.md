# NOTICE #
We are transitioning to github for hosting macsim releases.
Please visit https://github.com/macsimgt/macsim-public.git for simulator and https://github.com/macsimgt/macsim-traces.git for traces.

# Introduction #

  * MacSim is a heterogeneous architecture timing model simulator that is developed from Georgia Institute of Technology.
  * It simulates x86 and NVIDIA PTX instructions and it is a trace driven cycle level simulator. It models detailed micro-architectural behaviors, including pipeline stages, multi-threading, and memory systems.
  * MacSim is capable of simulating a variety of architecreus, such as Intel’s Sandy Bridge and NVIDIA’s Fermi. It can simulate homogeneous ISA multicore simulations as well as heterogeneous ISA multicore simulations. It also  supports, asymmetric multicore configurations (small cores + mediumcores + big cores) and SMT or MT architectures as well.
  * Currently interconnection network model (based on IRIS) and power model (based on McPAT)are connected.
  * ARM ISA support is on-progress.
  * MacSim is also one of the components of SST, so multiple MacSim simulators can run concurrently.


# Note #
  * We've developed a power model for GPU architecture using McPAT. Please refer to the following paper for more detailed information. [Power Modeling for GPU Architecture using McPAT](https://googledrive.com/host/0B2-rFvjUJRZfM1BDOWFvbmZEY1E/Power%20Modeling%20for%20GPU%20Architecture%20using%20McPAT.pdf) by Jieun Lim,  Nagesh B. Lakshminarayana,  Hyesoon Kim,  William Song,  Sudhakar Yalamanchili,  Wonyong Sung, from Transactions on Design Automation of Electronic Systems (TODAES) Vol. 19, No. 3.

# Documentation #

Please see [MacSim documentation file](https://macsim.googlecode.com/files/macsim_documentation_oct11.pdf) for more detailed descriptions.


# Download #
  * You can download tagged versions from this google code project homepage
  * or you can download the latest copy from our svn repository.
```
svn co https://svn.research.cc.gatech.edu/macsim/trunk macsim --username readonly
When you prompt password, please enter (there is no password).
```


# People #

  * Prof. Hyesoon Kim (Project Leader)
  * Jaekyu Lee (Main developer)
  * Nagesh B. Lakshminarayana (Main developer)
  * Jaewoong Sim (Main developer)
  * Jieun Lim (Power Modeling)
  * Tri Pho (SST-Macsim)


# Mailing list #

If you have a question, please send an email to macsim-dev@googlegroups.com, not directly to any developer


# Tutorial #

  * We had a tutorial in **HPCA-2012**. Please see http://comparch.gatech.edu/hparch/OcelotMacsim_tutorial.html for our tutorial slides.
  * We had a tutorial in **ISCA-2012**, http://comparch.gatech.edu/hparch/isca12_gt.html