# Some useful functions in R...

## Loading Data

### Load a table of data from a CSV file
```
iris <- read.csv( "iris.csv" )
```

### See the variables (column names) that are present in the table
```
str( iris )
```

### Get hold of a named column as a data vector
```
iris$sepal.width
```
---
## Displaying Data

### Load the datasets
```
titanic <- read.csv( "titanic.csv" )
iris <- read.csv( "iris.csv" )
```

### A frequency table
```
table( titanic$status )
```

### A bar chart
```
barplot( table( titanic$status ) )
```

### A histogram
```
hist( iris$petal.length, main="My Histogram", xlab="Petal length /cm" )
```

### A box plot
```
boxplot( iris$sepal.length, horizontal=TRUE, xlab="Sepal length /cm" )
```

### A scatter plot
```
plot( iris$petal.length, iris$petal.width, xlab="Petal length /cm", ylab="Petal width /cm" )
```

### Add a regression line
```
abline( lm( iris$petal.width ~ iris$petal.length ), col="red" )
```
---
## Descriptive Statistics

### The mean
```
mean( iris$sepal.length )
```

### The median
```
median( iris$sepal.length )
```

### A function to get the mode
```
getmode <- function(v) {
   uniqv <- unique(v)
   uniqv[which.max(table(match(v, uniqv)))]
}
getmode( titanic$status )
```

### The interquartile range
```
IQR( iris$sepal.length )
```

### The variance
```
var( iris$sepal.length )
```

### The standard deviation
```
sd( iris$sepal.length )
```

### Pearson correlation
```
cor( iris$petal.length, iris$petal.width )
```
