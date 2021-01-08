# install pip in windows 10

pip will installed automatically when python is installed

but after i installed python via chocoley: `choco install python`, i found pip was'nt there

i used `choco install pip`, but failed

i use the last resort: install from source:

1. download pip from <https://pypi.org/project/pip/#files>, i selected the 2nd file: pip-20.3.3.tar.gzip
2. unzip: 7-zip, the 1st step we get a tar file, then the 2nd step we get the result. we can see a folder
named pip-20.3.3, and there was a file "setup.py"
3. open powershell, cd to the folder "pip-20.3.3", run "python setup.py install", the prompt told me that 
pip is installed under "c:\python39\scripts"
4. add environment variable
5. in powershell, "pip --version", succeed! :smiley:
