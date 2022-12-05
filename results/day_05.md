Day 05
================
Lizzie
2022-12-05

- <a href="#day-5-supply-stacks" id="toc-day-5-supply-stacks">Day 5:
  supply stacks</a>
  - <a href="#part-1" id="toc-part-1">Part 1</a>
  - <a href="#part-2" id="toc-part-2">Part 2</a>

## Day 5: supply stacks

### Part 1

Write an algorithm to follow the instructions, moving a certain number
of crates (letters) from the top of one stack (end of one vector) to the
top (end) of another.

Crates are moved one at a time.

Aim: what crates end up on top of each stack?

``` r
## read data ----
# stacks <- readLines("../data/day_05.txt", n=9)
## NB. the stacks are reversed, so the top of each stack is the start of the vectors
stacks <- list(rev(c("N","R","G","P")),
               rev(c("J","T","B","L","F","G","D","C")),
               rev(c("M","S","V")),
               rev(c("L","S","R","C","Z","P")),
               rev(c("P","S","L","V","C","W","D","Q")),
               rev(c("C","T","N","W","D","M","S")),
               rev(c("H","D","G","W","P")),
               rev(c("Z","L","P","H","S","C","M","V")),
               rev(c("R","P","F","L","W","G","Z"))
               )

## TEST DATA
# stacks <- list(c("N","Z"),
#                c("D","C","M"),
#                c("P"))
# moves <- c("move 1 from 2 to 1",
#            "move 3 from 1 to 3",
#            "move 2 from 2 to 1",
#            "move 1 from 1 to 2")

## how to index in the list
stacks[[1]][1:2]
```

    ## [1] "P" "G"

``` r
## write and run algorithm ----
moves <- readLines("../data/day_05.txt")
```

    ## Warning in readLines("../data/day_05.txt"): incomplete final line found on '../
    ## data/day_05.txt'

``` r
moves <- moves[11:length(moves)]

stacks  # state at start
```

    ## [[1]]
    ## [1] "P" "G" "R" "N"
    ## 
    ## [[2]]
    ## [1] "C" "D" "G" "F" "L" "B" "T" "J"
    ## 
    ## [[3]]
    ## [1] "V" "S" "M"
    ## 
    ## [[4]]
    ## [1] "P" "Z" "C" "R" "S" "L"
    ## 
    ## [[5]]
    ## [1] "Q" "D" "W" "C" "V" "L" "S" "P"
    ## 
    ## [[6]]
    ## [1] "S" "M" "D" "W" "N" "T" "C"
    ## 
    ## [[7]]
    ## [1] "P" "W" "G" "D" "H"
    ## 
    ## [[8]]
    ## [1] "V" "M" "C" "S" "H" "P" "L" "Z"
    ## 
    ## [[9]]
    ## [1] "Z" "G" "W" "L" "F" "P" "R"

``` r
for (i in 1:length(moves)) {
  # i <- 1
  ## parse the instructions
  move <- moves[i]
  ## find the numbers
  move_n <- unlist(strsplit(move, "move | from | to "))
  move_n <- as.numeric(move_n[which(move_n != "")])
  n   <- move_n[1]  # how many to move
  sta <- move_n[2]  # from this stack
  end <- move_n[3]  # to this stack
  
  ## move j crates
  for (j in 1:n) {
    ## add the moved crate to the end stack
    # stacks[[sta]][1]  # the crate to move
    stacks[[end]] <- c(stacks[[sta]][1] , stacks[[end]])
    
    ## take away the moved crate from the start stack
    stacks[[sta]] <- stacks[[sta]][-1]
  }
  
  # cat("after step", i, "\n")
  # print(stacks)
  # cat("\n")
}

stacks  # state at end
```

    ## [[1]]
    ##  [1] "V" "V" "R" "R" "G" "M" "P" "D" "N" "P" "W" "S" "D" "F" "P" "Z" "Z" "R" "S"
    ## [20] "C" "T" "S" "L"
    ## 
    ## [[2]]
    ## [1] "P" "H" "G" "P"
    ## 
    ## [[3]]
    ## [1] "C" "P" "W"
    ## 
    ## [[4]]
    ## [1] "D" "Q" "H" "C" "T" "B" "L" "D" "L"
    ## 
    ## [[5]]
    ## [1] "M" "N" "V" "L" "F" "W" "C"
    ## 
    ## [[6]]
    ## [1] "S" "S" "M"
    ## 
    ## [[7]]
    ## [1] "L"
    ## 
    ## [[8]]
    ## [1] "W" "G"
    ## 
    ## [[9]]
    ## [1] "J" "Z" "C" "G"

``` r
### get answer ----

## concatenate the first letter in every stack
ans <- c()
for (i in 1:9) {
  ans <- c(ans, stacks[[i]][1])
}

paste(ans, collapse = "")
```

    ## [1] "VPCDMSLWJ"

### Part 2

Crates are now moved as a block instead of one at a time. (*i.e. the way
I wrote this code the first time round because I didn’t read the
question properly.*)

Aim: what crates end up on top of each stack now?

``` r
stacks <- list(rev(c("N","R","G","P")),
               rev(c("J","T","B","L","F","G","D","C")),
               rev(c("M","S","V")),
               rev(c("L","S","R","C","Z","P")),
               rev(c("P","S","L","V","C","W","D","Q")),
               rev(c("C","T","N","W","D","M","S")),
               rev(c("H","D","G","W","P")),
               rev(c("Z","L","P","H","S","C","M","V")),
               rev(c("R","P","F","L","W","G","Z"))
               )

stacks  # state at start
```

    ## [[1]]
    ## [1] "P" "G" "R" "N"
    ## 
    ## [[2]]
    ## [1] "C" "D" "G" "F" "L" "B" "T" "J"
    ## 
    ## [[3]]
    ## [1] "V" "S" "M"
    ## 
    ## [[4]]
    ## [1] "P" "Z" "C" "R" "S" "L"
    ## 
    ## [[5]]
    ## [1] "Q" "D" "W" "C" "V" "L" "S" "P"
    ## 
    ## [[6]]
    ## [1] "S" "M" "D" "W" "N" "T" "C"
    ## 
    ## [[7]]
    ## [1] "P" "W" "G" "D" "H"
    ## 
    ## [[8]]
    ## [1] "V" "M" "C" "S" "H" "P" "L" "Z"
    ## 
    ## [[9]]
    ## [1] "Z" "G" "W" "L" "F" "P" "R"

``` r
for (i in 1:length(moves)) {
  # i <- 1
  ## parse the instructions
  move <- moves[i]
  ## find the numbers
  move_n <- unlist(strsplit(move, "move | from | to "))
  move_n <- as.numeric(move_n[which(move_n != "")])
  n   <- move_n[1]  # how many to move
  sta <- move_n[2]  # from this stack
  end <- move_n[3]  # to this stack
  
  ## add the moved crate to the end stack
  # stacks[[sta]][1:n]  # the crate to move
  stacks[[end]] <- c(stacks[[sta]][1:n] , stacks[[end]])
  
  ## take away the moved crate from the start stack
  stacks[[sta]] <- stacks[[sta]][-c(1:n)]
  
  # cat("after step", i, "\n")
  # print(stacks)
  # cat("\n")
}

stacks  # state at end
```

    ## [[1]]
    ##  [1] "T" "C" "S" "V" "Q" "M" "S" "T" "V" "N" "G" "S" "C" "D" "J" "G" "L" "H" "P"
    ## [20] "D" "P" "W" "F"
    ## 
    ## [[2]]
    ## [1] "P" "L" "P" "R"
    ## 
    ## [[3]]
    ## [1] "W" "P" "H"
    ## 
    ## [[4]]
    ## [1] "C" "V" "B" "M" "S" "L" "L" "P" "Z"
    ## 
    ## [[5]]
    ## [1] "G" "R" "Z" "F" "Z" "L" "S"
    ## 
    ## [[6]]
    ## [1] "N" "R" "W"
    ## 
    ## [[7]]
    ## [1] "C"
    ## 
    ## [[8]]
    ## [1] "C" "D"
    ## 
    ## [[9]]
    ## [1] "G" "D" "M" "W"

``` r
### get answer ----

## concatenate the first letter in every stack
ans <- c()
for (i in 1:9) {
  ans <- c(ans, stacks[[i]][1])
}

paste(ans, collapse = "")
```

    ## [1] "TPWCGNCCG"

End.
