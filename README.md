# rdata

Data converted from R to CSV

## Jane Austen's books

```
$ conda activate r_env
$ R
> library(janeaustenr)
> write.csv(austen_books(), 'janeausten.csv', row.names=FALSE)
```
