MacSim 2.0 Release Note


1. MacSim's Trace Format has been changed along with the trace configuration file format. For a verification purpose, a few sample traces conforming to new trace file format are included in this release. For your convenience, more x86 sample traces from spec2006 will also be provided in googlecode page.
> - To make sure your installation is complete (./build.py), please go check using $MACSIM\_ROOT/bin/macsim binary. It searches for newly built executable and runs traces listed in trace\_file\_list to completion.
> - Please download sample traces provided in googlecode page and extract them under $MACSIM\_ROOT/trace/ directory. You may need to modify trace\_file\_list to run more traces other than the included ones.

2. MacSim is now compatible with Mac OS X.
> - We resolved a few compilation issues arises with Mac environment.
> - Please note that only g++-4.7 is fully tested and other versions of compilers are not yet fully supported.

3. Added SST-3.0.0 compatibility
> - There have been a lot of changes made to SST framework (Structured Simulation Toolkit presented by Sandia National Laboratory) since its last release. We have made a transition from an older version of SST APIs to a newer version to make it compatible with SST-3.0.0.