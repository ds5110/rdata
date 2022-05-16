# rdata

Data converted from R to CSV

## ISLR2

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


