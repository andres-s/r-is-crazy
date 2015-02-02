R is crazy
==========

*   There are two ways of handling default arguments that are just bad news:

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
    
        But you can't tell they're optional until your read the function definition.
        ```r
        i <- function(a, b) {
          c(missing(a), missing(b))
        }
        i()
        #> [1] TRUE TRUE
        ```

*   The names of base types are not used consistently throughout R, and type and
    the corresponding “is” function may use different names:
    ```r
    # The type of a function is "closure"
    f <- function() {}
    typeof(f)
    #> [1] "closure"
    is.function(f)
    #> [1] TRUE
    
    # The type of a primitive function is "builtin"
    typeof(sum)
    #> [1] "builtin"
    is.primitive(sum)
    #> [1] TRUE
    ```
