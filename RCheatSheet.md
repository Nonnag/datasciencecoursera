# R Cheat Sheet

### This will be a comprehensive "cheat sheet" of the R code covered in the Johns Hopkins Coursera Data Science course.

Compiled by Gannon McCollum from lecture notes by Jeff Leef, Roger Peng,
and Brian Caffo



## Code Examples

Code | Explanation
----------------- | ---------------------------------------------------
x <- 5 | Assign value 5 to variable x
x | Autoprint x
print(x) | Explicitly print x
x <- 1:20 | Assign the integer sequence containing values 1 through 20 to x

### Concatenation

Code | Explanation
----------------- | ---------------------------------------------------
x <- c(0.5, 0.6) | **CONCATENATES** (combines) a vector of numerical objects
x <- c(TRUE, FALSE) | Concatenates a vector of logical objects
x <- c(T, F) | Concatenates a vector of logical objects (just like above)
x <- c(1+0i, 2+4i) | Concatenates a vector of complex objects
x <- c("a", "b", "c") | Concatenates a vector of characters
x <- vector("numeric", length = 10) | creates a vector of 10 numeric objects, all with value 0

### Coercion

Code | Explanation
----------------- | ---------------------------------------------------
y <- c(TRUE, 2) | Concatenates (and coerces) a numerical vector of value [1, 2]
y <- c(1.7, "a") | Concatenates (and coerces) a character vector of value ["1.7", "a"]
class(y) | returns the class of y
as.numeric(x) | Explicitly coerces objects from the x class to numerical types
as.logical(x) | Explicitly coerces objects from the x class to logical types
as.character(x) | Explicitly coerces objects from the x class to character types
x <- list(1, "a", TRUE, 1 + 4i) | Creates a list with different object class types

### Matrices

Code | Explanation
----------------- | ---------------------------------------------------
m <- matrix(nrow = 2, ncol = 3) | Creates an empty 2 x 3 matrix
m <- matrix(1:6, nrow = 2, ncol = 3) | Creates an empty 2 x 3 matrix
dim(m) | returns the dimensions of m
attributes(m) | returns attributes (dimensions) of m
cbind(x, y) | combines x and y into a matrix where they each have their own columns.
rbind(x, y) | combines x and y into a matrix where they each have their own rows.

###Factors
Code | Explanation
----------------- | ---------------------------------------------------
x <- factor(c("yes", "yes", "no", "yes", "no")) | Creates a **FACTOR**
table(x) | returns the quantities of each type of **LEVEL**
attr(,"levels") | prints each unique level in the factor


## Misc. R Info

An **OBJECT** is a data structure having some attributes and methods which act
on its attributes.  Everything in R is an object.

R has five basic (or "atomic") classes of objects:
* character (strings)
* numeric (real numbers, think floats or double precision)
* integers
* complex (imaginary)
* logical (True/False, Boolean)

R objects can have attributes:
* names/dimnames
* dimensions (e.g. matrices, arrays)
* class
* length
* other user-defined attributes/metadata

When mixing different object classes into one vector, R will **COERCE** the different
elements into the same class.

If  explicit coersion isn't possible (e.g. coercing "a" to a numerical type),
then **NA** will be returned for all

**VECTORS** can only contain objects of the same class...

...But **LISTS**, which are expressed as vectors, can have multiple types of objects.

Empty vectors can be created with the **vector()** function.

Vectors are just one-row **MATRICES**, and their dimensions can be revised to turn them into matrices.

**FACTORS** are a special type of vector which are used to represent categorical data. Factors can be unordered or ordered.  One can think of a factor as an integer vector where each integer has a *label*.
* e.g., Having a variable that has values "male" and "female" is better than 1 and 2.
Factors are created with the factor() function.  
One attribute of factors are **LEVELS**
The *levels* argument can be used to establish a "baseline" level.


Some tricks for numbers:
* If you want an integer and not a number, use the **L** suffix
  * e.g., x <- 1 assigns a number while x <- 1L assigns an integers
* Special number **Inf** acts as infinity; e.g. 1 / Inf is 0
* **NaN** represents an undefined value ("not a number", 0 / 0)
