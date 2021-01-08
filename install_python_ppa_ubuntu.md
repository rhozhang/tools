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

