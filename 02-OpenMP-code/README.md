1. Load modules needed for compilation

        module load gcc/4.8.1

2. Compile the code with OpenMP 

        gcc -fopenmp hello_world_openmp.c -o hello.x

3. Prepare/Verify the submit script. Variable controlling the number
   of OpenMP threads i.e. OMP_NUM_THREADS is authomatically set on 
   Palmetto to the requested number of cores per node (`ncpus`). To change
   it use the following command

        export OMP_NUM_THREADS=x

   where `x` is the number of requested threads.

4. Submit the job 

        qsub job.sh


