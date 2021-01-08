# tinytex: install missing package

## non-R users

If you compile a LaTeX document and run into an error message like this:

    ! LaTeX Error: File `times.sty' not found.

    Type X to quit or <RETURN> to proceed,
    or enter new name. (Default extension: sty)

```bash
tlmgr search --global --file "/times.sty"
```

results:

    psnfss:
	texmf-dist/tex/latex/psnfss/times.sty
	
Find the package that contains the file with the exact name in the error log above. In this case, 
the missing package is psnfss, and we can install a package via tlmgr install

```bash
tlmgr install psnfss
```

## R Users

```r
library(tinytex)
tlmgr_search('/times.sty')   # search for times.sty
tlmgr_install('psnfss')      # install the psnfss package
tlmgr_update()               # update everything
```

## references

- <https://yihui.name/tinytex/>

