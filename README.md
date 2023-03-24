# rdata

Data converted from R to CSV using `write.table()` and `write.csv()`

* [write.table()](https://www.rdocumentation.org/packages/utils/versions/3.6.2/topics/write.table) -- rdocumentation.org
* `write.csv()` is also documented at this link. But `write.table()` makes more sense.
* `write.csv()` and `write.csv2()` are wrappers for `write.table()` and according to the documentation...
  * "These wrappers are deliberately inflexible: 
  * they are designed to ensure that the correct conventions are used to write a valid file. 
  * Attempts to change append, col.names, sep, dec or qmethod are ignored, with a warning."

## ISLR2 Wage data

`Wage` is a typical example of an ISLR2 dataset...

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

## NCI60 dataset

NCI60 microarray data -- expression levels of 6830 genes for 64 cancer cell lines

* In R, the NCI60 dataset is a list containing two elements: data and labs.
* `NCI60$data` is a 64-by-6830 matrix of the gene-expression values
* `NCI60$labs` is a 64-element vector of cancer-cell types (labels)
* These two objects are saved to separate CSV files as follows...
```
library(ISLR2)
write.table(NCI60$labs, 'NCI60labs.csv', row.names=FALSE, col.names=FALSE)
write.table(NCI60$data, 'NCI60data.csv', sep=",", row.names=FALSE, col.names=FALSE)
```
* [ISLR package](https://cran.r-project.org/web/packages/ISLR/ISLR.pdf) documentation -- pdf
* [ISLR2 package](https://cran.r-project.org/web/packages/ISLR2/ISLR2.pdf) documentation -- pdf

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
* [Reproducibility in R](https://stackoverflow.com/questions/5963269/how-to-make-a-great-r-reproducible-example) -- sfo

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
