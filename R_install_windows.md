# Installation

- Install the current version of R from <http://CRAN.R-project.org/bin/windows/base/>
- Install *Rtools* from <http://cran.at.r-project.org/bin/windows/Rtools/>

Suppose R is installed in the folder `d:/R`

# Change menu language as English
    
Edit file `d:/etc/Rconsole`, set the language as english: `language = english`

# set R mirror to ustc, set package directory
   
Edit file `d:/etc/Rprofile.site`, add the line below:

.libPaths("e:/rpkg")
   
#  Modified the mirror and set rpubs

Edit file `d:/etc/Rprofile.site`, add the line below:

options(repos = c(CRAN = "http://mirrors.ustc.edu.cn/CRAN",
                  CRANextra = "http://www.stats.ox.ac.uk/pub/RWin"),
        rpubs.upload.method = "internal")

#  change timezone

Edit file `d:/etc/Rprofile.site`, add the line below:

Sys.setenv(TZ='Asia/Shanghai')

# Add Welcome information

Edit file `d:/etc/Rprofile.site`, add the line below:

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

# package update

Whenever R's new version appear, remove the old one, install the latest one, and enter this command:

update.packages(lib.loc = "e:/rpkg", checkBuilt = TRUE, ask = FALSE)
