# Meaning vs Syntax

## Functions

```python
def weird_addition(number1, number2):
    result = 2 * (number1 + number2)
    return result
```

```R
weird_addition <- function(number1,number2){
    result <- 2 * (number1 + number2)
    return(result)
}
```

```julia
function weird_addition(number1, number2)
    result = 2 * (number1 + number2)
    return result
end
```

## import code

```python
import pandas as pd
import argparse
```

```R
library("dyplr")
library("argparse")
```

```julia
using DataFrames
using ArgParse
```

## Use the REPL

```python
>>> x = "look at me, I'm a string!”
>>> x
"look at me, I'm a string!”
>>> 5 ** 2
25
```

```R
> x <- "Look at me, I'm a string!”
> x
[1] "Look at me, I'm a string!”
> 5 ^ 2
[1] 25
```

```julia
julia> x = "Look at me, I'm a String!”
"Look at me, I'm a String!”
julia> 5 ^ 2
25
```

## Use collections

```python
d = {"apple": "green", "banana": "yellow", "orange": "orange"}

d["banana"] # "yellow"

l = [1, 1.2, "a"]

l[1] # 1.2
```

```R
l <- c(1, 1.2, "a")
l[2] # "1.2"
```

```julia
d = Dict("apple"=> "green", "banana"=> "yellow", "orange"=> "orange")
d["banana"] # "yellow"
l = [1, 1.2, "a"]
l[2] # 1.2
```
