# rdata

$ conda activate r_env
$ R
> library(janeaustenr)
> write.csv(austen_books(), 'austen_books.csv', row.names=FALSE)
