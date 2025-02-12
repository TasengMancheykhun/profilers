# Profilers
**Intel's Vtune Profiler** 
* Set Up Environment Variables
  * `source /opt/intel/oneapi/vtune/latest/env/vars.sh`

  * To make it permanent, add the above line to ~/.bashrc or ~/.bash_profile:
  * `echo 'source /opt/intel/oneapi/vtune/latest/env/vars.sh' >> ~/.bashrc`
  * `source ~/.bashrc`

* Hotspot analysis type:
  * `vtune -collect hotspots -result-dir vtune_results ./exe`
    * `hotspots`: Identifies CPU-intensive functions
    * `result-dir vtune_results`: Stores profiling data in `vtune_results/`.
 
  * Summary:
    * Elapsed time: Total time taken by the program to complete
    * CPU Time:  

**Nvidia's Nsight systems**
  * `nsys profile --trace=cuda,nvtx,mpi,openmp -o profile_output mpirun -np 8 ./exe`
  * This generates a report `profile_output.nsys-rep`
  * Run `nsys-ui profile_output.nsys-rep`
