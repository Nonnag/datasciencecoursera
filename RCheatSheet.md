# R Cheat Sheet

### This will be a comprehensive "cheat sheet" of the R code covered
### in the Johns Hopkins Coursera Data Science course.

### Compiled by Gannon McCollum from lecture notes by Jeff Leef, Roger Peng,
### and Brian Caffo


## Code Examples

x <- 5     Assign value 5 to variable x
x          Autoprint x
print(x)   Explicitly print x

x <- 1:20  Assign the integer sequence containing values 1 through 20 to x

## Misc. R Info
R has five basic (or "atomic") classes of **OBJECTS**:
* character (strings)
* numeric (real numbers, think floats or double precision)
* integers
* complex (imaginary)
* logical (True/False, Boolean)

**VECTORS** can only contain objects of the same class...
...But **LISTS**, which are expressed as vectors, can have multiple types of objects.

Empty vectors can be created with the **vector()** function.

Some tricks for numbers:
* If you want an integer and not a number, use the **L** suffix
  * e.g., x <- 1 assigns a number while x <- 1L assigns an integers
* Special number **Inf** acts as infinity; e.g. 1 / Inf is 0
* **NaN** represents an undefined value ("not a number", 0 / 0)
