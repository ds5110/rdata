# R stuff

## R data types

Notes from [Advanced R](http://adv-r.had.co.nz/) (1st edition)...

* R has 5 data types:
  * 3 homogeneous data structures: atomic vector (1-D), matrix (2-D), array (n-D)
  * 2 heterogeneous data structures: list, data frame
* `str()` prints info about the structure of an R any object
* There are no scalar (0-D) types in R -- strings and numbers are vectors of length one

Notes from [Advanced R](https://adv-r.hadley.nz/introduction.html) (2nd edition)...

* vectors: the most important family data types in R -- there are "two flavours of vectors":
  * atomic vectors: all elements have the same type
  * lists: elements can have different types (elements of lists are references)
  * NULL: not a vector, but closely related and often serves the role of a zero-length vector
* every vector can have attributes
  * attributes can be thought of as a "named list of arbitrary metadata"
  * "you can think of attributes as name-value pairs that attach metadata to an object"
  * get and set attributes with `attr()`, get the all with `attributes()` and set a bunch with `structure()`
  * "Attributes should generally be thought of as ephemeral" -- "most attributes are lost by most operations"
* data structures not included in atomic vectors:
  * matrices
  * arrays
  * factors
  * date-times

## References

...by Hadley Wickham

* [Advanced R](http://adv-r.had.co.nz/) (1st edition)
  * [Data structures](http://adv-r.had.co.nz/Data-structures.html)
    * Discussion of basic data types in R
  * [Functional programming](http://adv-r.had.co.nz/Functional-programming.html#functional-programming)
    * Discussion of R as a functional programming language
* [Advanced R](https://adv-r.hadley.nz/introduction.html) (2nd edition)
  * [Advanced R: Introduction](https://adv-r.hadley.nz/introduction.html) (2nd edition)
    * Answers the question: "Why R?"
    * Honest discussion of pros and cons -- and introduction of DRY
* [R for Data Science](https://r4ds.had.co.nz/)

## NCI60 dataset

Microarray data has 6830 measurements of 64 cancer-cell lines.

* a list containing two elements: data and labs.
  * data is a 64 by 6830 matrix of the expression values
  * labs is a vector listing the cancer types for the 64 cell lines.
* Each cell line has a cancer-type label (`nci.labs`)
* Data (`nci.data`) has 64 rows and 6830 columns

```
library(ISLR2)
nci.labs <- NCI60$labs
nci.data <- NCI60$data
```

* `typeof(NCI60)` returns "list", which is a heterogeneous data structure in R
  * In R, the other heterogeneous data structure is a data frame

## NCI 60 References

* ISLR Ref: https://rdrr.io/cran/ISLR/man/NCI60.html
* ISLR2 Ref: https://rdrr.io/cran/ISLR2/man/NCI60.html
* NCI-60 human cancer cell-line screen
  * This is an application of the NCI 60 cell line
  * [Cell list](https://dtp.cancer.gov/discovery_development/nci-60/cell_list.htm) -- cancer.gov
  * [Methodology](https://dtp.cancer.gov/discovery_development/nci-60/methodology.htm) -- cancer.gov 
* ESL refs
  * Example 4 (p5 & 6) -- DNA expression microarrays
    * Nice high-level description the dataset -- DNA expression for the NCI 60 cell line
    * 6830 rows represent the gene-expression measurements
    * 64 column represent the different cancer cell lines
  * Section 14.3.8 (p512) -- K-means
    * Depends on: "K" and starting configuration
  * Section 14.3.12 (p520-7) -- Hierarchical clustering
    * Depends on: dissimilarity measure, clustering strategy (e.g., agglomerative/bottom-up, divisive/top-down)
* ISLR2 refs
  * Section 12.5.4 (p542-7) NCCI60 Data Example
    * Unsupervised learning lab
    * Labels are used after the fact to see if clustering is successful at grouping like-cancer types
  * PCA
    * Measurements of gene expression range from -6 to 6
    * Scaling before PCA is done, but it's arguable about whether or not scaling should be used
