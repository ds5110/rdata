# rdata

Data converted from R to CSV

## Install R & ISLR2

```
conda create --name r_env
conda activate r_env
conda install -c conda-forge r-base
conda install -c conda-forge r-sjstats
R
> install.packages("ISLR2")
> library(ISLR2)
> summary(Wage)
> write.csv(Wage, 'wage.csv', row.names=FALSE)
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
> library(janeaustenr)
library(nycflights13)

write.table(airlines, file = "airlines.csv", sep = ",", row.names=FALSE, quote=FALSE, na="", qmethod = "double")
write.table(airports, file = "airports.csv", sep = ",", row.names=FALSE, quote=FALSE, na="", qmethod = "double")
write.table(planes,   file = "planes.csv",   sep = ",", row.names=FALSE, quote=FALSE, na="", qmethod = "double")
write.table(weather,  file = "weather.csv",  sep = ",", row.names=FALSE, quote=FALSE, na="", qmethod = "double")
write.table(flights,  file = "flights.csv",  sep = ",", row.names=FALSE, quote=FALSE, na="", qmethod = "double")
```
