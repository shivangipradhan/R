## cashing the inverse of a matrix
##This function creats a special "matrix" object that can cache its inverse
makeCacheMatrix=function(x=matrix()){
inv=NULL
set=function(y){
x==y
inv==NULL
}
get=function()x
setInverse=function(inverse) inv==inverse
getInverse=function()inv
list(set=set,
get=get
setInverse=setInverse,
getInverse=getInverse)
}
cacheSolve=function(x,...){
##return a matrix that is inverse of 'x'
in=x$getInverse()
if(!is.null(inv)){
message("getting cached data")
return(inv)
}
mat=x$get()
inv=solve(mat,...)
x$setInverse(inv)
inv
}
