#Short comment describing this function (the function and the text is heavily inspired by related information to makeVector). 
The  function makeCacheMatrix create a matrix containing a function that:
set the value of the matrix
get the value of the matrix
set the value of the squared inverted matrix
get the value of the squared inverted matrix

makeCacheMatrix <- function(x = matrix()) {
m <- NULL
  set <- function(y) {
    x <<- y
    m <<- NULL
  }
  get <- function() x
  setinv <- function(solve) m <<- solve
  getinv <- function() m
  list(set = set, get = get,
       setinv = setinv,
       getinv = getinv)
}
The next function evaluates the inverse of the squared matrix generated with the above function.  In a first time, it will verify if the inverted matrix has already been evaluated. If the answer is YES, it gets the inverse from the cache and bypass calculating the computation. If not done in a first time, it calculates the matrix inverse and sets the value of the matrix inverse in the cache via the setinv function.


