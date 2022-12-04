Day 04
================
Lizzie
2022-12-04

- <a href="#day-4-camp-cleanup" id="toc-day-4-camp-cleanup">Day 4: camp
  cleanup</a>
  - <a href="#part-1" id="toc-part-1">Part 1</a>
  - <a href="#part-2" id="toc-part-2">Part 2</a>

## Day 4: camp cleanup

### Part 1

The first range of numbers is the section that elf 2 is doing; the
second is elf 2. We’re interested in the overlaps - where both elves
have been told to clean the same section of the camp.

Aim: in how many pairs does one fully contain the other?

``` r
input <- readLines("../data/day_04.txt")
```

    ## Warning in readLines("../data/day_04.txt"): incomplete final line found on '../
    ## data/day_04.txt'

``` r
get_vectors <- function(t) {
  t_exp <- unlist(strsplit(t, ","))
  t_exp <- gsub("-", ":", t_exp)
  t_exp <- paste("c(", t_exp, ")", sep="")
  
  v1 <- eval(parse(text = t_exp[1]))
  v2 <- eval(parse(text = t_exp[2]))
  
  return(list(v1, v2))
}

input[1]
```

    ## [1] "48-50,48-49"

``` r
get_vectors(input[1])
```

    ## [[1]]
    ## [1] 48 49 50
    ## 
    ## [[2]]
    ## [1] 48 49

``` r
## how many where one fully contains the other?
tot <- 0
for (i in 1:length(input)) {
  # i <- 1  # testing
  v1 <- get_vectors(input[i])[[1]]
  v2 <- get_vectors(input[i])[[2]]
  ## does one fully contain the other?
  if(length(intersect(v1, v2)) == length(v1) | length(intersect(v1, v2)) == length(v2)) {
    tot <- tot + 1
  }
}

tot
```

    ## [1] 530

### Part 2

Aim: in how many pairs is there any intersection at all?

``` r
## how many where they intersect at all?
tot <- 0
for (i in 1:length(input)) {
  # i <- 1  # testing
  v1 <- get_vectors(input[i])[[1]]
  v2 <- get_vectors(input[i])[[2]]
  ## does one fully contain the other?
  if(length(intersect(v1, v2)) > 0) {
    tot <- tot + 1
  }
}

tot
```

    ## [1] 903

End.
