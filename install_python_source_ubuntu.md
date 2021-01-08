# installing python3.9 on ubuntu from source

1. installing dependencies necessary to build python

     sudo apt update
     sudo apt install build-essential zlib1g-dev libncurses5-dev libgdbm-dev libnss3-dev libssl-dev \
                      libreadline-dev libffi-dev libsqlite3-dev wget libbz2-dev

2. download the latest release's source code from [python official site](https://www.python.org/downloads/source/)

     wget wget https://www.python.org/ftp/python/3.9.1/Python-3.9.1.tgz

3. extract the gzipped archive

     tar -xf Python-3.9.0.tgz

4. configure

     cd Python-3.9.0
     ./configure --enable-optimizations

option --enable-optimizations optimizes the python binary by running multiple tests

5. build

    make -j 12

For faster build time, modify the -j to correspond to the number of cores in your processor. 
You can find the number by typing `nproc`

6. install python binaries

     sudo make altinstall

Using *altinstall* instead of *install* to overwrite the default system python3 binary later

7. verify

     python3.9 --version

python on git: <https://github.com/deadsnakes/python3.9>
