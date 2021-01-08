# installation

## secure apt

```bash
sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-keys E298A3A825C0D65DFD57CBB651716619E084DAB9
```

## setting repository

- method 1:

```bash
sudo apt-add-repository -y "deb https://mirrors.aliyun.com/CRAN/bin/linux/ubuntu focal-cran40/"
```

- method 2:

```bash
sudo gedit /etc/apt/sources.list
```

add this line to the file above: 

`deb https://mirrors.aliyun.com/CRAN/bin/linux/ubuntu focal-cran40/`

## update

```bash
sudo apt-get update
```

## install

```bash
sudo apt-get install build-essential r-base-core r-base-dev r-base-html r-doc-html
```

# upgrade

```
sudo apt-get upgrade
```

# setting

## Set R default language as English

```bash
sudo gedit /etc/R/Renviron
```

Add the line below:

LANGUAGE = 'en'

## set R mirror as aliyun

```bash
sudo gedit /etc/R/Rprofile.site
```

Add the following lines: 

options(repos = 'http://mirrors.aliyun.com/CRAN', 
        rpubs.upload.method = 'internal')

You can add any R command to this file, e.g.

# .First <- function(){
#           cat("\nWelcome to R, Rho! It's", date(), ".\n Have a good day. \n\n")}

.First <- function(){
   dttm <- Sys.time()
   wdd <- format(dttm, "%w")  # week day in digit format
   wds <- switch(wdd, "0" = "Sun", "1" = "Mon", "2" = "Tue", "3" = "Wed",
                 "4" = "Thu", "5" = "Fri", "6" = "Sat")
   cat("\nWelcome to R, Rho. It's ", wds, " || ",
       format(dttm, "%H:%M:%S %Y-%m-%d"), "\n\n")
}
              
## Set added packages installation path as "~/rpkg"

```bash
sudo gedit /etc/R/Renviron.site
```

Add the following line:

R_LIBS = ~/rpkg

## Change timezone

```bash
sudo gedit /etc/R/Renviron.site
```

add this line:

TZ = 'Asia/Shanghai'

To search R's package in *.deb* format, call to <http://launchpad.net>.
