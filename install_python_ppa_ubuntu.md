# install python with deadsnakes ppa

1. Update the packages list and install the prerequisites

     sudo apt update
     sudo apt install software-properties-common

2. Add the deadsnakes ppa to sources list

     sudo add-apt-repository ppa:deadsnakes/ppa

When prompted, press "enter" to continue

3. install

     sudo apt install python3.9

4. verify

     python3.9 --version
     
**NB**: use "python3.9" instead of "python3", "python3" will point to default python3 (python 3.8.5 for ubuntu 20.04),

5. install pip

Pip is included by default in python 3.4 and later. use `python3.9 -m pip --version` to check if pip is there

If, for some reason, pip is not installed, install it manually

```bash
sudo apt install python3.9-distutils
curl https://bootstrap.pypa.io/get-pip.py -o get-pip.py
python3.9 get-pip.py
rm get-pip.py
```

6. install package with pip

```bash
python3.9 -m pip install SomePackage
```

