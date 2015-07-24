1. Load modules needed for compilation

        module load gcc/4.8.1 openmpi/1.6.4

2. Compile the code

        mpicc pi_mpi.c -o pi.x 

3. Prepare/Verify the submit script. OpenMPI on Palmetto is aware of all PBS 
   variables. There is no need to specify the number of processes with `mpirun`.
   OpenMPI will automatically parse the `$PBS_NODEFILE` file. To make sure that 
   all CPU cores will be used for MPI processes use `mpiprocs` equal to `ncpus`
   in the hardware request line of PBS script, e.g.

        #PBS -l select=2:ncpus=16:mpiprocs=16

   will allow `mpirun` to start 32 processes.

4. Submit the job

        qsub job.sh
