R is crazy
==========

*   **Default function arguments can refer to variables declared in the function body**
    ```r
    h <- function(a = 1, b = d) {
      d <- (a + 1) ^ 2
      c(a, b)
    }
    h()
    #> [1] 1 4
    ```
    
*   **Can handle optional function arguments using `missing()`**

    But you can't tell they're optional until your read the function definition!
    ```r
    i <- function(a, b) {
      c(missing(a), missing(b))
    }
    i()
    #> [1] TRUE TRUE
    ```
