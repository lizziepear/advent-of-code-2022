Day 01
================
Lizzie
2022-12-01

- <a href="#day-1-calorie-counting" id="toc-day-1-calorie-counting">Day 1:
  calorie counting</a>
  - <a href="#part-1" id="toc-part-1">Part 1</a>
  - <a href="#part-2" id="toc-part-2">Part 2</a>

## Day 1: calorie counting

### Part 1

Aim: read the data, each elf is separated by a blank line, sum the
numbers for each elf and find the one that’s carrying the most calories.

``` r
## read data from file
c <- readLines("../data/day_01_1.txt")
```

    ## Warning in readLines("../data/day_01_1.txt"): incomplete final line found on
    ## '../data/day_01_1.txt'

``` r
head(c, n=10)
```

    ##  [1] "7769"  "6798"  "11685" "10826" "11807" "5786"  "7932"  ""      "54883"
    ## [10] ""

``` r
## make a df to store the sum for each elf
df <- data.frame(n_elf = numeric(), n_cal = numeric())
t_elf <- 1
t_cal <- 0
for (i in 1:length(c)) {
  if (c[i] != "") {
    t_cal <- t_cal + as.numeric(c[i])
  } else if (c[i] == "") {
    row <- data.frame(n_elf = t_elf, n_cal = t_cal)
    df <- rbind(df, row) # add to df
    t_elf <- t_elf + 1 # next elf
    t_cal <- 0  # reset
  }
}

head(df)
```

    ##   n_elf n_cal
    ## 1     1 62603
    ## 2     2 54883
    ## 3     3 63535
    ## 4     4 51464
    ## 5     5 46036
    ## 6     6 41569

``` r
## find the elf carrying the most calories - how many?
max(df$n_cal)
```

    ## [1] 71780

### Part 2

How many calories are the top three elves (by number of calories)
carrying?

``` r
## sort in reverse order of n_cal
df <- df[order(-df$n_cal), ]
head(df)
```

    ##     n_elf n_cal
    ## 35     35 71780
    ## 225   225 71481
    ## 76     76 69228
    ## 122   122 68704
    ## 149   149 68474
    ## 159   159 68254

``` r
## sum first three n_cal
sum(df$n_cal[1:3])
```

    ## [1] 212489

End.
