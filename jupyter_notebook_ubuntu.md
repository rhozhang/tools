# jupyter notebook on ubuntu

## prerequisites

Jupyter supports **Ju**lia, **Pyt**hon, **R**, Haskell, and Ruby, etc, but jupyter notebook itself depends on python
 (python 3.3 or higher, python 2.7)

## install with pip

```bash
python3 -m pip install --upgrade pip
python3 -m pip install jupyter
```

## run jupyter with python

```bash
cd <mydirectory>
jupyter notebook
```

## run jupyter with julia

install IJulia with `add IJulia` on julia pkg mode

method 1: from julia repl

```julia
using IJulia
notebook(detached = true)
```

Setting detached as true to launch a notebook server in the background that will persist even when you quit Julia.
This is also useful if you want to keep using the current Julia session instead of opening a new one

By default, the notebook "dashboard" opens in your home directory (homedir()), but you can open the dashboard in
a different directory with notebook(dir="/some/path")

method 2: from terminal

```bash
cd <mydirectory>
jupyter notebook
```

## run jupyter with r

install libs required:

```bash
sudo apt-get install libzmq3-dev libssl-dev libcurl​4-openssl-dev
```

install r packages:

```r
install.packages(c('repr', 'IRdisplay', 'evaluate', 'crayon', 'pbdZMQ', 'devtools', 'uuid', 'digest'))
install.packages('IRkernel')
IRkernel::installspec()   # to register the kernel in the current R installation
```

```bash
cd <mydirectory>
jupyter notebook
```

new --> choose r as your tool
