### Data Import/export

`read.csv` or `read.table` are 2 important functions available in base R to read **.csv** and **.txt** files.  These are the most commanly used functions for reading in biological datasets unless the data is read from database servers.

**SYNTAX**
```R
#read.table(file=fileName.csv, header = FALSE, sep = "",dec = ".",row.names, col.names, as.is = !stringsAsFactors,
#           na.strings = "NA",stringsAsFactors = default.stringsAsFactors())
```
**Other Variants**
```R
#read.csv(file, header = TRUE, sep = ",", quote = "\"",
#         dec = ".", fill = TRUE, comment.char = "", ...)
#
#read.csv2(file, header = TRUE, sep = ";", quote = "\"",
#          dec = ",", fill = TRUE, comment.char = "", ...)

#read.delim(file, header = TRUE, sep = "\t", quote = "\"",
#           dec = ".", fill = TRUE, comment.char = "", ...)

#read.delim2(file, header = TRUE, sep = "\t", quote = "\"",
#            dec = ",", fill = TRUE, comment.char = "", ...) 

```
### Data from other Statistical tools

Functions to read data from common statistical tools is given in **Table1**

:Table1

|Function   |Format   |
|:----------|:--------:|
|read.spss  | SPSS    |
|read.dta   | Stata   |
|read.ssd   | SAS     |
|read.octave| Octave  |
|read.mtp   | Minitab |
|read.systat| Systat  |

visit [https://www.datacamp.com/community/tutorials/r-data-import-tutorial](https://www.datacamp.com/community/tutorials/r-data-import-tutorial)  for a Comprehensive Data Import tutorial covering everything from importing simple text files to the more advanced SPSS and SAS files.


### R Binary Files

The ideal way of passing on data or any R object between R users is to use `RData` files format.  Rdata objects are binary files and can be passed to users without the issue of OS on the host system.

#### Saving RData

**SYNTAX**<break/>
`save(object(s),file="fileName.rdata")`

**e.g**
```R
chip2<-data.frame(Gene=c("Gene1","Gene2","Gene3","Gene4","Gene5","Gene6","Gene7","Gene8","Gene9","Gene10"), 
Chromosome = c("Chr1","Chr1","Chr1","Chr1","Chr2","Chr2","Chr2","Chr3","Chr3","Chr4"), Position=c(11234,21234,25452,32414,156009,297862,299220,312112,141789,13114), 
Enrichment=c(2,2.3,3.5,2.8,1.98,2.76,3.76,2.45,NA,3.4))
#
#Saving the object
save(chip2,file="enrichment.rdata")
#
selectedPosn=c(12312,57867,46587)
SampleName="Sample1"
ReadDepth=124546654
#
#Saving the above all 4 objects in RData format
save(chip2,selectedPosn,SampleName,ReadDepth,file="compact.rdata")

```
#### Reading Rdata
```R
load("compact.rdata")
```
### Data included with R

Often R packages comes with datasets for users to try the vignette of the package.e.g **diamonds** dataset with ggplot2.

```R
library(ggplot2)
data(diamonds)
head(diamonds)
```

######################################################################################
