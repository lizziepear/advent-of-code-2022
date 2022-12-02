Day 02
================
Lizzie
2022-12-02

- <a href="#day-2-rock-paper-scissors"
  id="toc-day-2-rock-paper-scissors">Day 2: rock paper scissors</a>
  - <a href="#part-1" id="toc-part-1">Part 1</a>
  - <a href="#part-2" id="toc-part-2">Part 2</a>

## Day 2: rock paper scissors

### Part 1

The first column is what your opponent is going to play: A for Rock, B
for Paper, and C for Scissors. The second column must be what you play:
X for Rock, Y for Paper, and Z for Scissors.

Your total score is the sum of your scores for each round. The score for
a single round is the score for the shape you selected (1 for Rock, 2
for Paper, and 3 for Scissors) plus the score for the outcome of the
round (0 if you lost, 3 if the round was a draw, and 6 if you won).

Aim: calculate your total score for all rounds.

``` r
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
## read data from file
df <- read.table("../data/day_02_1.txt")
colnames(df) <- c("opp", "me")
head(df)
```

    ##   opp me
    ## 1   C  Z
    ## 2   B  Y
    ## 3   C  X
    ## 4   B  Z
    ## 5   C  Y
    ## 6   B  Y

``` r
## table of scores
tab <- data.frame(opp      = c("A","A","A","B","B","B","C","C","C"),
                  me       = c("X","Y","Z","X","Y","Z","X","Y","Z"),
                  my_score = c( 4 , 8 , 3 , 1 , 5 , 9 , 7 , 2 , 6 ))

## merge in
df_1 <- left_join(df, tab)
```

    ## Joining, by = c("opp", "me")

``` r
## what's my total score?
sum(df_1$my_score)
```

    ## [1] 11386

### Part 2

Actually, X = lose, Y = draw, Z = win.

``` r
colnames(df) <- c("opp", "my_res")

## table of scores
tab <- data.frame(opp      = c("A","A","A","B","B","B","C","C","C"),
                  me       = c("r","p","s","r","p","s","r","p","s"),
                  my_res   = c("Y","Z","X","X","Y","Z","Z","X","Y"),
                  my_score = c( 4 , 8 , 3 , 1 , 5 , 9 , 7 , 2 , 6 ))

## merge in
df_2 <- left_join(df, tab)
```

    ## Joining, by = c("opp", "my_res")

``` r
head(df_2)
```

    ##   opp my_res me my_score
    ## 1   C      Z  r        7
    ## 2   B      Y  p        5
    ## 3   C      X  p        2
    ## 4   B      Z  s        9
    ## 5   C      Y  s        6
    ## 6   B      Y  p        5

``` r
## my total score
sum(df_2$my_score)
```

    ## [1] 13600

End.
