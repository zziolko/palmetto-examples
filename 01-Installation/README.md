1. Download the source code 

        wget http://ftp.gnu.org/gnu/hello/hello-2.10.tar.gz

2. Unpack the downloaded file

        tar zxvf hello-2.10.tar.gz

3. Load modules needed for compilation

        module load gcc/4.8.1

4. Compile and install the program

        cd hello-2.10
        ./configure --prefix=$HOME/software/hello
        make
        make install

5. Test the installation

        export PATH=$HOME/software/hello/bin:$PATH
        hello

