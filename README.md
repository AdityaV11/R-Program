# R-Program
# Coursera-R-program
#R programming
CacheMatrix <- function(mtx = matrix()) {
    inve <- NULL
    set <- function(x) {
      mtx <<- x;
       inve <<- NULL;
   }     get <- function() return(mtx);
    setinv <- function(inv) inve <<- inv;
    getinv <- function() return(inve);
    return(list(set = set, get = get, setinv = setinv, getinv = getinv))
} cacheSolve <- function(mtx, ...) {
    inve <- mtx$getinv()
    if(!is.null(inve)) {
        message("Getting cached data...")
        return(inve)
    }    data <- mtx$get()
    invserse <- solve(data, ...)
    mtx$setinv(inve)
    return(inve)
}
