# R Cheat Sheet

### This will be a comprehensive "cheat sheet" of the R code covered
### in the Johns Hopkins Coursera Data Science course.

Compiled by Gannon McCollum from lecture notes by Jeff Leef, Roger Peng,
and Brian Caffo



## Code Examples

Code | Explanation
----------------- | ---------------------------------------------------
x <- 5 | Assign value 5 to variable x
x | Autoprint x
print(x) | Explicitly print x
x <- 1:20 | Assign the integer sequence containing values 1 through 20 to x
x <- c(0.5, 0.6) | **CONCATENATES** (combines) a vector of numerical objects
x <- c(TRUE, FALSE) | Concatenates a vector of logical objects
x <- c(T, F) | Concatenates a vector of logical objects (just like above)
x <- c(1+0i, 2+4i) | Concatenates a vector of complex objects
x <- c("a", "b", "c") | Concatenates a vector of characters

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

**VECTORS** can only contain objects of the same class...

...But **LISTS**, which are expressed as vectors, can have multiple types of objects.

Empty vectors can be created with the **vector()** function.

Some tricks for numbers:
* If you want an integer and not a number, use the **L** suffix
  * e.g., x <- 1 assigns a number while x <- 1L assigns an integers
* Special number **Inf** acts as infinity; e.g. 1 / Inf is 0
* **NaN** represents an undefined value ("not a number", 0 / 0)
