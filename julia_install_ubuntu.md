# install julia on ubuntu

## download

[ustc mirror]<http://mirrors.ustc.edu.cn/julia-releases/bin/linux/x64/1.5/julia-1.5.3-linux-x86_64.tar.gz>

## install dependencies

Building Julia requires that the following software be installed:

- GNU make — building dependencies.
- gcc & g++ (>= 4.7) or Clang (>= 3.1, Xcode 4.3.3 on OS X) — compiling and linking C, C++.
- libatomic — provided by gcc and needed to support atomic operations.
- python (>=2.7) — needed to build LLVM.
- gfortran — compiling and linking Fortran libraries.
- perl — preprocessing of header files of libraries.
- wget, curl, or fetch (FreeBSD) — to automatically download external libraries.
- m4 — needed to build GMP.
- awk — helper tool for Makefiles.
- patch — for modifying source code.
- cmake (>= 3.4.3) — needed to build libgit2.
- pkg-config — needed to build libgit2 correctly, especially for proxy support.

On Debian-based distributions (e.g. Ubuntu), you can easily install them with apt-get:

```bash
sudo apt-get install build-essential libatomic1 python gfortran perl wget m4 cmake pkg-config
sudo apt-get install git
```

## install

```bash
mkdir app_rho
tar -xvzf Downloads/sftwr/julia-1.5.3-linux-x86_64.tar.gz --directory app_rho
cd app_rho/julia-1.5.3
pwd   # <julia-path>
```

## create a symbolic link to julia

```bash
sudo ln -s /home/rho/app_rho/julia-1.5.3/bin/julia /usr/local/bin/julia
```

An alternative way is putting the "/home/rho/app_rho/julia-1.5.3/bin/" path in your system $PATH variable 

```bash
echo PATH=\$PATH:/home/rho/app_rho/julia-1.5.3/bin/ >> ~/.profile
source ~/.profile
```

## use julia

```bash
julia
```

## welcome info

```bash
echo 'println("Hi, Rho. Welcome to Julia.")' > ~/.julia/config/startup.jl
```

## updating

julia-1.5.2 --> julia-1.5.3

**NB**: the following words come from my self-trial, not from any material in the web

- remove the folder "julia-1.5.2" in "app_rho"
- download julia-1.5.3 from ustc's mirrors
- cd app_rho
- tar -xvzf Downloads/sftwr/julia-1.5.3-linux-x86_64.tar.gz --directory app_rho
- cd app_rho/julia-1.5.3
- sudo rm sudo ln -s /home/rho/app_rho/julia-1.5.3/bin/julia /usr/local/bin/julia/usr/local/bin/julia
- enter "julia" in terminal to open julia
- in pkg mode, enter "update"

