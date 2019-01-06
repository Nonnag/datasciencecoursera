# R Cheat Sheet

### This will be a comprehensive R "cheat sheet" as covered in the Johns Hopkins Coursera Data Science course.

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
m <- matrix(1:6, nrow = 2, ncol = 3) | Creates a 2 x 3 matrix with values 1 through 6
dim(m) | returns the dimensions of m
attributes(m) | returns attributes (dimensions) of m
cbind(x, y) | combines x and y into a matrix where they each have their own columns.
rbind(x, y) | combines x and y into a matrix where they each have their own rows.

### Factors

Code | Explanation
----------------- | ---------------------------------------------------
x <- factor(c("yes", "yes", "no", "yes", "no")) | Creates a **FACTOR**
table(x) | returns the quantities of each type of **LEVEL**
attr(,"levels") | prints each unique level in the factor

### Data Types - Names Attribute

Code | Explanation
----------------- | ---------------------------------------------------
x <- 1:3 | creates vector x with values 1 through 3
names(x) | Returns the names of objects
names(x) <- c("foo", "bar", "norf") | assigns names to the corresponding objects
dimnames(m) <- list(c("a", "b"), c("c", "d")) | Names columns and rows of matrix m


### Data Frames

Code | Explanation
----------------- | ---------------------------------------------------

### Reading Data

Function Name | Purpose | Analagous Function
--- | --- | ---
read.table and read.csv | to read tabular data | write.table
readLines | to read a line of a text file | writeLines
source | for reading in R code files (inverse of dump) | dump
dget | for reading in R code files (inverse of dput) | dput
load | for reading in saved workspaces | save
unserialize | for reading single R objects in binary form | unserialize

## Function Info

### read.table

Important arguments:
* file:  the name of a file, or a connection
* header:  logical indicating if the file has a header line
* sep:  a string indicating how the columns are separated
* colClasses:  a character vector indicating the class of each column in the dataset
* nrows:  the number of rows in the dataset
* comment.char:  a character string indicating the comment character
* skip:  the number of lines to skip from the beginning
* stringAsFactors:  should character variables be coded as factors?

**data <- read.table("foo.txt")**

For the above code, R will automatically:
* skip lines that begin with #
* figure out how many rows there are (and how much memory needs to be allocated)
* figure what type of variable is in each column of the table.  Telling R all these things directly makes R run faster and more efficiently
* read.csv is identical to read.table except the default separator is a comma.

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

NaN and NA:
* **NaN** represents an undefined value ("not a number", 0 / 0)
* **NA** represents everything else that NaN doesn't, and can have a class
* a NaN value is also NA, but the converse is not true.

**DATA FRAMES**:
* Data frames are used to store tabular data (spreadsheets).
They're represented as a special type of list where every element of the list has to have the same length.
Each element of the list can be thought of as a column, and the length of each element of the list is the number of rows.
Unlike matrices, data frames can store different classes of objects in each column (just like lists); matrices must have every element be the same class.
* Data frames also have a special attribute called **row.names**
* Data frames are usually created by calling **read.table()** or **read.csv()**
* Can be converted to a matrix by calling **data.matrix**
