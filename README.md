# NS-3 simulator for RDMA and updated to run over DCQCN with TCD
This is an NS-3 simulator for RDMA over Converged Ethernet v2 (RoCEv2). It includes the implementation of DCQCN + TCD, TIMELY, PFC, ECN and Broadcom shared buffer switch.

It is based on NS-3 version 3.17, and ported to Visual Studio environment, as explained [here](https://www.nsnam.org/wiki/Ns-3_on_Visual_Studio_2012).  

## Note
TIMELY implementation is in "timely" branch and hasn't been merged into the master branch. So, you may not be able to simulate DCQCN and TIMELY simultaneously at this moment.

## Quick Start

### Build
To compile it out-of-the-box, you need Visual Studio *2015* (not 2013 or 2017). 
People have successfully built it with *free* version, 
which can be downloaded [here](https://imagine.microsoft.com/en-us/Catalog/Product/101). 
Open windows/ns-3-dev/ns-3-dev.sln, just build the whole solution.

If you cannot get a Windows machine or Visual Studio for any reason, you may try building it with the original Makefile. We have done it a while back, but now you probably need to edit a few things in waf to make it work.

### Run
The binary will be generated at windows/ns-3-dev/x64/Release/main.exe.
We included configuration files for 4 separate scenarios under windows/ns-3-dev/x64/Release/sim_config.
Scenarios include single congestion, multi congestion, victim flows, and fairness. 
Execute main.exe in windows/ns-3-dev/x64/Release/:
```
cd windows\ns-3-dev\x64\Release\
main.exe sim_config\single_congestion\config.txt

### Updates
We updated the original [NS-3 Simulator](https://github.com/bobzhuyb/ns3-rdma) Repo to include TCD implmentation over DCQCN. We also added the sim_config which includes all the scenarios we configured for testing TCD. 

