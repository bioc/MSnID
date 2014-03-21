MSnID
=====

utilities for handling MS/MS proteomic identifications

to install run the `MSnID`:

```r
# add path to Bioconductor repositories
source("http://bioconductor.org/biocLite.R")
options(repos=biocinstallRepos(character()))

install.packages("devtools")
library("devtools")
install_github("MSnID", "vladpetyuk")

# installing dependencies from GitHub to ensure latest versions
install_github("MSnbase", "lgatto")
install_github("mzID", "thomasp85", quick=TRUE)
```

as an example download and run c_elegans.R script into your working directory
```r
download.file("https://raw2.github.com/vladpetyuk/MSnID/master/examples/c_elegans.R", 
              "c_elegans.R", method='curl')
```


A brief description:
* Input: mzIdentML files with MS/MS search results
* The package utilities assess the data confidence metrics 
  (MS/MS match scoring, parent ion mass measurement accuracy, missed cleavages ...)
* Optimization of filtering criteria for MS/MS matches to achieve the most number
  of identifications within a pre-defined FDR limit.
* Convertion to MSnSet object for quantitative analysis
