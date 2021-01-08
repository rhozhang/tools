# FTP Client in Ubuntu

## wget and wput

To pull a file from ftp, we can use wget; to push a file to ftp, use wput. By default, wget has been installed on your Ubuntu.

```bash
sudo apt-get install wput
wget -O "~/Downloads/sp.csv" "ftp://zsqdo:@10.1.12.5/data/sp500.csv"
wput <mylocalfile> "ftp://zsqup::10.1.12.5/R/file_name.R"
```

## ftp clent

Using ftp client, we can interact with ftp more freely.

### connect

```bash
ftp 10.1.12.5
# enter name and password to login
# if anonymous ftp server, Name: anonymous; password: <empty>
```

### working with directories

- ls: list directories or files
- cd: change directory
- mkdir: create directory
- lcd: change local directory

### pull file

```bash
cd do/data
lcd ~/Downloads
get sp500.csv
```

### push file

- put: push single file
- mput: push multiple files

```bash
mput *.R
```

### closing connection

bye, quit, or exit
