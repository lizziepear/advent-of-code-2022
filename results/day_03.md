Day 03
================
Lizzie
2022-12-04

- <a href="#day-3-rucksack-reorganisation"
  id="toc-day-3-rucksack-reorganisation">Day 3: rucksack
  reorganisation</a>
  - <a href="#part-1" id="toc-part-1">Part 1</a>
  - <a href="#part-2" id="toc-part-2">Part 2</a>
- <a href="#day-3-by-chatgpt" id="toc-day-3-by-chatgpt">Day 3, by
  chatGPT</a>

## Day 3: rucksack reorganisation

### Part 1

Each line of text contains the objects in a rucksack, half in one
compartment and half in the other compartment. Find the item type that
appears in both compartments and store than for all rucksacks.

Aim: sum the priority scores of all the resulting items

``` r
input <- readLines("../data/day_03.txt")
```

    ## Warning in readLines("../data/day_03.txt"): incomplete final line found on '../
    ## data/day_03.txt'

``` r
matches <- vector(mode="character", length=length(input))

## find the items appearing in both compartments
for (i in 1:length(input)) {
  # i <- 1  # testing
  t_in <- input[i]
  t_split <- as.character(unlist(strsplit(t_in, "")))
  t_first <- t_split[1:(length(t_split)/2)]
  t_second <- t_split[((length(t_split)/2)+1):length(t_split)]
  ## find the matching object
  matches[i] <- t_first[which(t_first %in% t_second)]
}
```

    ## Warning in matches[i] <- t_first[which(t_first %in% t_second)]: number of items
    ## to replace is not a multiple of replacement length

    ## Warning in matches[i] <- t_first[which(t_first %in% t_second)]: number of items
    ## to replace is not a multiple of replacement length

    ## Warning in matches[i] <- t_first[which(t_first %in% t_second)]: number of items
    ## to replace is not a multiple of replacement length

    ## Warning in matches[i] <- t_first[which(t_first %in% t_second)]: number of items
    ## to replace is not a multiple of replacement length

    ## Warning in matches[i] <- t_first[which(t_first %in% t_second)]: number of items
    ## to replace is not a multiple of replacement length

    ## Warning in matches[i] <- t_first[which(t_first %in% t_second)]: number of items
    ## to replace is not a multiple of replacement length

    ## Warning in matches[i] <- t_first[which(t_first %in% t_second)]: number of items
    ## to replace is not a multiple of replacement length

    ## Warning in matches[i] <- t_first[which(t_first %in% t_second)]: number of items
    ## to replace is not a multiple of replacement length

    ## Warning in matches[i] <- t_first[which(t_first %in% t_second)]: number of items
    ## to replace is not a multiple of replacement length

    ## Warning in matches[i] <- t_first[which(t_first %in% t_second)]: number of items
    ## to replace is not a multiple of replacement length

    ## Warning in matches[i] <- t_first[which(t_first %in% t_second)]: number of items
    ## to replace is not a multiple of replacement length

    ## Warning in matches[i] <- t_first[which(t_first %in% t_second)]: number of items
    ## to replace is not a multiple of replacement length

    ## Warning in matches[i] <- t_first[which(t_first %in% t_second)]: number of items
    ## to replace is not a multiple of replacement length

    ## Warning in matches[i] <- t_first[which(t_first %in% t_second)]: number of items
    ## to replace is not a multiple of replacement length

    ## Warning in matches[i] <- t_first[which(t_first %in% t_second)]: number of items
    ## to replace is not a multiple of replacement length

    ## Warning in matches[i] <- t_first[which(t_first %in% t_second)]: number of items
    ## to replace is not a multiple of replacement length

    ## Warning in matches[i] <- t_first[which(t_first %in% t_second)]: number of items
    ## to replace is not a multiple of replacement length

    ## Warning in matches[i] <- t_first[which(t_first %in% t_second)]: number of items
    ## to replace is not a multiple of replacement length

    ## Warning in matches[i] <- t_first[which(t_first %in% t_second)]: number of items
    ## to replace is not a multiple of replacement length

    ## Warning in matches[i] <- t_first[which(t_first %in% t_second)]: number of items
    ## to replace is not a multiple of replacement length

    ## Warning in matches[i] <- t_first[which(t_first %in% t_second)]: number of items
    ## to replace is not a multiple of replacement length

    ## Warning in matches[i] <- t_first[which(t_first %in% t_second)]: number of items
    ## to replace is not a multiple of replacement length

    ## Warning in matches[i] <- t_first[which(t_first %in% t_second)]: number of items
    ## to replace is not a multiple of replacement length

    ## Warning in matches[i] <- t_first[which(t_first %in% t_second)]: number of items
    ## to replace is not a multiple of replacement length

    ## Warning in matches[i] <- t_first[which(t_first %in% t_second)]: number of items
    ## to replace is not a multiple of replacement length

    ## Warning in matches[i] <- t_first[which(t_first %in% t_second)]: number of items
    ## to replace is not a multiple of replacement length

    ## Warning in matches[i] <- t_first[which(t_first %in% t_second)]: number of items
    ## to replace is not a multiple of replacement length

    ## Warning in matches[i] <- t_first[which(t_first %in% t_second)]: number of items
    ## to replace is not a multiple of replacement length

    ## Warning in matches[i] <- t_first[which(t_first %in% t_second)]: number of items
    ## to replace is not a multiple of replacement length

    ## Warning in matches[i] <- t_first[which(t_first %in% t_second)]: number of items
    ## to replace is not a multiple of replacement length

    ## Warning in matches[i] <- t_first[which(t_first %in% t_second)]: number of items
    ## to replace is not a multiple of replacement length

    ## Warning in matches[i] <- t_first[which(t_first %in% t_second)]: number of items
    ## to replace is not a multiple of replacement length

    ## Warning in matches[i] <- t_first[which(t_first %in% t_second)]: number of items
    ## to replace is not a multiple of replacement length

    ## Warning in matches[i] <- t_first[which(t_first %in% t_second)]: number of items
    ## to replace is not a multiple of replacement length

    ## Warning in matches[i] <- t_first[which(t_first %in% t_second)]: number of items
    ## to replace is not a multiple of replacement length

    ## Warning in matches[i] <- t_first[which(t_first %in% t_second)]: number of items
    ## to replace is not a multiple of replacement length

    ## Warning in matches[i] <- t_first[which(t_first %in% t_second)]: number of items
    ## to replace is not a multiple of replacement length

    ## Warning in matches[i] <- t_first[which(t_first %in% t_second)]: number of items
    ## to replace is not a multiple of replacement length

    ## Warning in matches[i] <- t_first[which(t_first %in% t_second)]: number of items
    ## to replace is not a multiple of replacement length

    ## Warning in matches[i] <- t_first[which(t_first %in% t_second)]: number of items
    ## to replace is not a multiple of replacement length

    ## Warning in matches[i] <- t_first[which(t_first %in% t_second)]: number of items
    ## to replace is not a multiple of replacement length

    ## Warning in matches[i] <- t_first[which(t_first %in% t_second)]: number of items
    ## to replace is not a multiple of replacement length

    ## Warning in matches[i] <- t_first[which(t_first %in% t_second)]: number of items
    ## to replace is not a multiple of replacement length

    ## Warning in matches[i] <- t_first[which(t_first %in% t_second)]: number of items
    ## to replace is not a multiple of replacement length

    ## Warning in matches[i] <- t_first[which(t_first %in% t_second)]: number of items
    ## to replace is not a multiple of replacement length

    ## Warning in matches[i] <- t_first[which(t_first %in% t_second)]: number of items
    ## to replace is not a multiple of replacement length

    ## Warning in matches[i] <- t_first[which(t_first %in% t_second)]: number of items
    ## to replace is not a multiple of replacement length

    ## Warning in matches[i] <- t_first[which(t_first %in% t_second)]: number of items
    ## to replace is not a multiple of replacement length

    ## Warning in matches[i] <- t_first[which(t_first %in% t_second)]: number of items
    ## to replace is not a multiple of replacement length

    ## Warning in matches[i] <- t_first[which(t_first %in% t_second)]: number of items
    ## to replace is not a multiple of replacement length

    ## Warning in matches[i] <- t_first[which(t_first %in% t_second)]: number of items
    ## to replace is not a multiple of replacement length

    ## Warning in matches[i] <- t_first[which(t_first %in% t_second)]: number of items
    ## to replace is not a multiple of replacement length

    ## Warning in matches[i] <- t_first[which(t_first %in% t_second)]: number of items
    ## to replace is not a multiple of replacement length

    ## Warning in matches[i] <- t_first[which(t_first %in% t_second)]: number of items
    ## to replace is not a multiple of replacement length

    ## Warning in matches[i] <- t_first[which(t_first %in% t_second)]: number of items
    ## to replace is not a multiple of replacement length

    ## Warning in matches[i] <- t_first[which(t_first %in% t_second)]: number of items
    ## to replace is not a multiple of replacement length

    ## Warning in matches[i] <- t_first[which(t_first %in% t_second)]: number of items
    ## to replace is not a multiple of replacement length

    ## Warning in matches[i] <- t_first[which(t_first %in% t_second)]: number of items
    ## to replace is not a multiple of replacement length

    ## Warning in matches[i] <- t_first[which(t_first %in% t_second)]: number of items
    ## to replace is not a multiple of replacement length

    ## Warning in matches[i] <- t_first[which(t_first %in% t_second)]: number of items
    ## to replace is not a multiple of replacement length

    ## Warning in matches[i] <- t_first[which(t_first %in% t_second)]: number of items
    ## to replace is not a multiple of replacement length

    ## Warning in matches[i] <- t_first[which(t_first %in% t_second)]: number of items
    ## to replace is not a multiple of replacement length

    ## Warning in matches[i] <- t_first[which(t_first %in% t_second)]: number of items
    ## to replace is not a multiple of replacement length

    ## Warning in matches[i] <- t_first[which(t_first %in% t_second)]: number of items
    ## to replace is not a multiple of replacement length

    ## Warning in matches[i] <- t_first[which(t_first %in% t_second)]: number of items
    ## to replace is not a multiple of replacement length

    ## Warning in matches[i] <- t_first[which(t_first %in% t_second)]: number of items
    ## to replace is not a multiple of replacement length

    ## Warning in matches[i] <- t_first[which(t_first %in% t_second)]: number of items
    ## to replace is not a multiple of replacement length

    ## Warning in matches[i] <- t_first[which(t_first %in% t_second)]: number of items
    ## to replace is not a multiple of replacement length

    ## Warning in matches[i] <- t_first[which(t_first %in% t_second)]: number of items
    ## to replace is not a multiple of replacement length

    ## Warning in matches[i] <- t_first[which(t_first %in% t_second)]: number of items
    ## to replace is not a multiple of replacement length

    ## Warning in matches[i] <- t_first[which(t_first %in% t_second)]: number of items
    ## to replace is not a multiple of replacement length

    ## Warning in matches[i] <- t_first[which(t_first %in% t_second)]: number of items
    ## to replace is not a multiple of replacement length

    ## Warning in matches[i] <- t_first[which(t_first %in% t_second)]: number of items
    ## to replace is not a multiple of replacement length

    ## Warning in matches[i] <- t_first[which(t_first %in% t_second)]: number of items
    ## to replace is not a multiple of replacement length

    ## Warning in matches[i] <- t_first[which(t_first %in% t_second)]: number of items
    ## to replace is not a multiple of replacement length

    ## Warning in matches[i] <- t_first[which(t_first %in% t_second)]: number of items
    ## to replace is not a multiple of replacement length

    ## Warning in matches[i] <- t_first[which(t_first %in% t_second)]: number of items
    ## to replace is not a multiple of replacement length

    ## Warning in matches[i] <- t_first[which(t_first %in% t_second)]: number of items
    ## to replace is not a multiple of replacement length

    ## Warning in matches[i] <- t_first[which(t_first %in% t_second)]: number of items
    ## to replace is not a multiple of replacement length

    ## Warning in matches[i] <- t_first[which(t_first %in% t_second)]: number of items
    ## to replace is not a multiple of replacement length

    ## Warning in matches[i] <- t_first[which(t_first %in% t_second)]: number of items
    ## to replace is not a multiple of replacement length

    ## Warning in matches[i] <- t_first[which(t_first %in% t_second)]: number of items
    ## to replace is not a multiple of replacement length

    ## Warning in matches[i] <- t_first[which(t_first %in% t_second)]: number of items
    ## to replace is not a multiple of replacement length

    ## Warning in matches[i] <- t_first[which(t_first %in% t_second)]: number of items
    ## to replace is not a multiple of replacement length

    ## Warning in matches[i] <- t_first[which(t_first %in% t_second)]: number of items
    ## to replace is not a multiple of replacement length

    ## Warning in matches[i] <- t_first[which(t_first %in% t_second)]: number of items
    ## to replace is not a multiple of replacement length

    ## Warning in matches[i] <- t_first[which(t_first %in% t_second)]: number of items
    ## to replace is not a multiple of replacement length

    ## Warning in matches[i] <- t_first[which(t_first %in% t_second)]: number of items
    ## to replace is not a multiple of replacement length

    ## Warning in matches[i] <- t_first[which(t_first %in% t_second)]: number of items
    ## to replace is not a multiple of replacement length

    ## Warning in matches[i] <- t_first[which(t_first %in% t_second)]: number of items
    ## to replace is not a multiple of replacement length

    ## Warning in matches[i] <- t_first[which(t_first %in% t_second)]: number of items
    ## to replace is not a multiple of replacement length

    ## Warning in matches[i] <- t_first[which(t_first %in% t_second)]: number of items
    ## to replace is not a multiple of replacement length

    ## Warning in matches[i] <- t_first[which(t_first %in% t_second)]: number of items
    ## to replace is not a multiple of replacement length

    ## Warning in matches[i] <- t_first[which(t_first %in% t_second)]: number of items
    ## to replace is not a multiple of replacement length

    ## Warning in matches[i] <- t_first[which(t_first %in% t_second)]: number of items
    ## to replace is not a multiple of replacement length

    ## Warning in matches[i] <- t_first[which(t_first %in% t_second)]: number of items
    ## to replace is not a multiple of replacement length

    ## Warning in matches[i] <- t_first[which(t_first %in% t_second)]: number of items
    ## to replace is not a multiple of replacement length

    ## Warning in matches[i] <- t_first[which(t_first %in% t_second)]: number of items
    ## to replace is not a multiple of replacement length

    ## Warning in matches[i] <- t_first[which(t_first %in% t_second)]: number of items
    ## to replace is not a multiple of replacement length

    ## Warning in matches[i] <- t_first[which(t_first %in% t_second)]: number of items
    ## to replace is not a multiple of replacement length

    ## Warning in matches[i] <- t_first[which(t_first %in% t_second)]: number of items
    ## to replace is not a multiple of replacement length

    ## Warning in matches[i] <- t_first[which(t_first %in% t_second)]: number of items
    ## to replace is not a multiple of replacement length

    ## Warning in matches[i] <- t_first[which(t_first %in% t_second)]: number of items
    ## to replace is not a multiple of replacement length

    ## Warning in matches[i] <- t_first[which(t_first %in% t_second)]: number of items
    ## to replace is not a multiple of replacement length

    ## Warning in matches[i] <- t_first[which(t_first %in% t_second)]: number of items
    ## to replace is not a multiple of replacement length

    ## Warning in matches[i] <- t_first[which(t_first %in% t_second)]: number of items
    ## to replace is not a multiple of replacement length

    ## Warning in matches[i] <- t_first[which(t_first %in% t_second)]: number of items
    ## to replace is not a multiple of replacement length

    ## Warning in matches[i] <- t_first[which(t_first %in% t_second)]: number of items
    ## to replace is not a multiple of replacement length

    ## Warning in matches[i] <- t_first[which(t_first %in% t_second)]: number of items
    ## to replace is not a multiple of replacement length

    ## Warning in matches[i] <- t_first[which(t_first %in% t_second)]: number of items
    ## to replace is not a multiple of replacement length

    ## Warning in matches[i] <- t_first[which(t_first %in% t_second)]: number of items
    ## to replace is not a multiple of replacement length

``` r
## sum their priority scores
df <- data.frame(let = matches)

## tab of priority scores
tab <- data.frame(let = c(letters, LETTERS), num = c(1:52))
head(tab)
```

    ##   let num
    ## 1   a   1
    ## 2   b   2
    ## 3   c   3
    ## 4   d   4
    ## 5   e   5
    ## 6   f   6

``` r
tail(tab)
```

    ##    let num
    ## 47   U  47
    ## 48   V  48
    ## 49   W  49
    ## 50   X  50
    ## 51   Y  51
    ## 52   Z  52

``` r
## merge in
library(dplyr)
```

    ## 
    ## Attaching package: 'dplyr'

    ## The following objects are masked from 'package:stats':
    ## 
    ##     filter, lag

    ## The following objects are masked from 'package:base':
    ## 
    ##     intersect, setdiff, setequal, union

``` r
df_new <- dplyr::left_join(df, tab)
```

    ## Joining, by = "let"

``` r
head(df_new)
```

    ##   let num
    ## 1   m  13
    ## 2   w  23
    ## 3   V  48
    ## 4   p  16
    ## 5   q  17
    ## 6   D  30

``` r
sum(df_new$num)
```

    ## [1] 7568

### Part 2

Find the matches between each set of 3 elves (3 lines), and sum the
priorities

``` r
badges <- vector(mode="character")

for (i in seq(1, length(input), 3)) {
  # i <- 1  # testing
  i_vec <- input[i:(i+2)]
  i_1 <- unlist(strsplit(i_vec[1], ""))
  i_2 <- unlist(strsplit(i_vec[2], ""))
  i_3 <- unlist(strsplit(i_vec[3], ""))
  m1 <- i_1[which(i_1 %in% i_2)]
  m2 <- unique(i_3[which(i_3 %in% m1)])
  stopifnot(length(m2)==1)
  ## add to results
  badges <- c(badges, m2)
}

df <- data.frame(let = badges)
df_new <- dplyr::left_join(df, tab)
```

    ## Joining, by = "let"

``` r
head(df_new)
```

    ##   let num
    ## 1   Q  43
    ## 2   Q  43
    ## 3   v  22
    ## 4   m  13
    ## 5   P  42
    ## 6   m  13

``` r
sum(df_new$num)
```

    ## [1] 2780

End.

## Day 3, by chatGPT

``` r
# Here is one way you could write a function in R to check whether a 
# single-letter character string is upper case or not:
is_upper <- function(x) {
  # Check if x is a single-letter character string
  if (nchar(x) != 1) return(FALSE)
  
  # Convert x to upper case
  x_upper <- toupper(x)
  
  # Check if x is upper case
  x_upper == x
}

# Define a function that takes a character and returns its priority
# as defined in the problem statement
get_char_priority <- function(c) {
  # Convert the character to a raw vector
  c_raw <- as.integer(charToRaw(c))

  # Check if the character is uppercase or lowercase
  if (is_upper(c)) {
    # For uppercase letters, subtract the raw vector for 'A'
    # to compute the priority
    A_raw <- as.integer(charToRaw("A"))
    priority <- as.integer(c_raw - A_raw) + 27
  } else {
    # For lowercase letters, subtract the raw vector for 'a'
    # to compute the priority
    a_raw <- as.integer(charToRaw("a"))
    priority <- as.integer(c_raw - a_raw) + 1
  }

  # Return the priority of the given character
  return(priority)

}

input <- readLines("../data/day_03.txt")
```

    ## Warning in readLines("../data/day_03.txt"): incomplete final line found on '../
    ## data/day_03.txt'

``` r
# define function 
find_common_item_priority <- function(items) {
  # Split the string of items into two equal-length substrings
  half_length <- nchar(items) %/% 2
  comp1 <- substr(items, 1, half_length)
  comp2 <- substr(items, half_length + 1, nchar(items))

  # Create vectors of the unique characters in each compartment
  unique1 <- unique(unlist(strsplit(comp1, "")))
  unique2 <- unique(unlist(strsplit(comp2, "")))

  # Find the common item type by taking the intersection of the
  # two vectors of unique characters
  common_item_type <- intersect(unique1, unique2)

  # Convert the common item type to a raw vector and extract the
  # first element (since there is only one common item type)
  common_item_raw <- get_char_priority(common_item_type[1])

  # Convert the raw vector to an integer and return the result
  return(as.integer(common_item_raw))
}

## find the answer
find_common_item_priority(input[2])  # test
```

    ## [1] 23

``` r
v <- as.numeric(sapply(input, find_common_item_priority))
head(v)
```

    ## [1] 13 23 48 16 17 30

``` r
sum(v)
```

    ## [1] 7568

Took a lot of prompting to update the code such that it actually worked,
but we got the final answer in the end!

Shall we do part 2? Maybe another time…

End.
