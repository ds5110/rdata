# rdata

Data converted from R to CSV

## R data types

* R has 5 data types:
  * 3 homogeneous data structures: atomic vector (1-D), matrix (2-D), array (n-D)
  * 2 heterogeneous data structures: list, data frame
* `str()` prints info about the structure of an R any object
* There are no scalar (0-D) types in R -- strings and numbers are vectors of length one
* Ref: [Data structures in R](http://adv-r.had.co.nz/Data-structures.html) -- Hadley Wickham

## Wage dataset

A typical example of ISLR2 data...

```
conda activate r_env
R
> install.packages("ISLR2")
> library(ISLR2)
> summary(Wage)
> write.csv(Wage, 'wage.csv', row.names=FALSE)
> quit()
conda deactivate
```

## NC160 dataset

* Microarray data has 6830 measurements of 64 cancer-cell lines.
* Each cell line has a cancer-type label (`nci.labs`)
* Data (`nci.data`) has 64 rows and 6830 columns

```
library(ISLR2)
nci.labs <- NCI60$labs
nci.data <- NCI60$data
```

* `typeof(NCI60)` returns "list", which is a heterogeneous data structure in R
  * In R, the other heterogeneous data structure is a data frame

## Install R & ISLR2

```
conda create --name r_env
conda activate r_env
conda install -c conda-forge r-base
conda install -c conda-forge r-sjstats
conda deactivate
```

* [ISLR2 cran repo](https://rdrr.io/cran/ISLR2/) -- rdrr.io
* [conda install](https://docs.anaconda.com/anaconda/install/) (maybe just miniconda) -- anaconda.com
* [miniconda install](https://docs.conda.io/en/latest/miniconda.html) -- docs.conda.io
* [managing environments](https://docs.conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html)
* [r-base install](https://anaconda.org/conda-forge/r-base)

## ISLR2 data

```
$ conda activate r_env
$ R
> library(IRLR2)
> write.csv(Wage, 'Wage.csv', row.names=FALSE)
```

## Jane Austen's books

```
$ conda activate r_env
$ R
> library(janeaustenr)
> write.csv(austen_books(), 'janeausten.csv', row.names=FALSE)
```

## nycflights13 dataset

```
$ conda activate r_env
$ R
> library(nycflights13)

write.table(airlines, file = "airlines.csv", sep = ",", row.names=FALSE, quote=FALSE, na="", qmethod = "double")
write.table(airports, file = "airports.csv", sep = ",", row.names=FALSE, quote=FALSE, na="", qmethod = "double")
write.table(planes,   file = "planes.csv",   sep = ",", row.names=FALSE, quote=FALSE, na="", qmethod = "double")
write.table(weather,  file = "weather.csv",  sep = ",", row.names=FALSE, quote=FALSE, na="", qmethod = "double")
write.table(flights,  file = "flights.csv",  sep = ",", row.names=FALSE, quote=FALSE, na="", qmethod = "double")
```
