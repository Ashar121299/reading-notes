## What is a jupyter lab ?

_*upyterLab enables you to work with documents and activities such as Jupyter notebooks, text editors, terminals, and custom components in a flexible,
integrated, and extensible manner.*_

_*ou can arrange multiple documents and activities side by side in the work area using tabs and splitters. Documents and activities integrate with each other,
enabling new workflows for interactive computing,*_

_*JupyterLab also offers a unified model for viewing and handling data formats. JupyterLab understands many file formats (images, CSV, JSON, Markdown, PDF, Vega, Vega-Lite, etc.)
and can also display rich kernel output in these formats.*_

### JupyterLab Releases

_*the releases of JupyterLab are suitable for general daily use by both Jupyter novices and users experienced with the Classic Notebook interface. As of the 1.0 release (June 2019),
it is additionally ready for extension writers who wish to further customize the JupyterLab experience for others.*_


#### Hint : JupyterLab will eventually replace the classic Jupyter Notebook. Throughout this transition,
#### the same notebook document format will be supported by both the classic Notebook and JupyterLab.

## NumPy Tutorial: Data Analysis with Python

_*NumPy is a commonly used Python data analysis package. By using NumPy, we can speed up our workflow, 
and interface with other packages in the Python ecosystem, like scikit-learn, that use NumPy under the hood. *_

### Lists Of Lists for CSV Data


_*This way without numpy and it use for SSV (semicolon separated value ) its just need to import csv library and open the csv file, after that we create csv.reader
object and pass through a ";" to make sure that the records are split up on the semicolon character instead of the default comma character,finally 
Call the list type to get all the rows from the file.*_


### Numpy 2-Dimensional Arrays

_*In fact, it’s just a different way of thinking about a list of lists. A matrix has rows and columns.
By specifying a row number and a column number, we’re able to extract an element from a matrix.*_


_*In a NumPy array, the number of dimensions is called the rank, and each dimension is called an axis. So the rows are the first axis,
and the columns are the second axis.*_

#### Creating A NumPy Array

_*We can create a NumPy array using the numpy.array function. If we pass in a list of lists, it will automatically create a NumPy array with the same number of rows 
and columns. Because we want all of the elements in the array to be float elements for easy computation, we’ll leave off the header row, which contains strings. 
One of the limitations of NumPy is that all the elements in an array have to be of the same type, so if we include the header row, 
all the elements in the array will be read in as strings. Because we want to be able to do computations like find the average quality of the wines,
we need the elements to all be floats.*_


#### Alternative NumPy Array Creation Methods

_*There are a variety of methods that you can use to create NumPy arrays. To start with, you can create an array where every element is zero.*_ 

empty_array = np.zeros((3,4))

It’s useful to create an array with all zero elements in cases when you need an array of fixed size, but don’t have any values for it yet.


_*we can also create an array where each element is a random number using numpy.random.rand.*_

np.random.rand(3,4)

Creating arrays full of random numbers can be useful when you want to quickly test your code with sample arrays.

#### Slicing NumPy Arrays

_*If we instead want to select the first three items from the fourth column, we can do it using a colon (:).
A colon indicates that we want to select all the elements from the starting index up to but not including the ending index*_

wines[0:3,3]

#### Assigning Values To NumPy Arrays

_*We can also use indexing to assign values to certain elements in arrays. We can do this by assigning directly to the indexed value:*_

wines[1,5] = 10

### 1-Dimensional NumPy Arrays

_*NumPy is a package for working with multidimensional arrays. One of the most common types of multidimensional arrays is the 1-dimensional array, or vector.
 A 1-dimensional array only needs a single index to retrieve an element. Each row and column in a 2-dimensional array is a 1-dimensional array.like a list of lists 
 is analogous to a 2-dimensional array,a single list is analogous to a 1-dimensional array.*_
 
 
 ### N-Dimensional NumPy Arrays
 
 _*there are cases when you’ll want to deal with arrays that have greater than 3 dimensions. One way to think of this is as a list of lists of lists. *_
 
 Adding more dimensions can make it much easier to query your data if it’s organized in a certain way. As we go from 3-dimensional arrays to 4-dimensional
 and larger arrays, the same properties apply, and they can be indexed and sliced in the same ways.
 
 ### NumPy Data Types 
 
 *_Each NumPy array can store elements of a single data type. NumPy stores values using its own data types, which are distinct from Python types like float and str.
 This is because the core of NumPy is written in a programming language called C, which stores data differently than the Python data types. NumPy data types map
 between Python and C, allowing us to use NumPy arrays without any conversion hitches.*_
 
 #### Converting Data Types
 
 _*We can use the numpy.ndarray.astype method to convert an array to a different type. The method will actually copy the array,
 and return a new array with the specified data type.*_
 
 ### NumPy Array Operations
 
 _*NumPy makes it simple to perform mathematical operations on arrays. This is one of the primary advantages of NumPy,
 and makes it quite easy to do computations.*_
 
#### Single Array Math

If you do any of the basic mathematical operations (/, *, -, +, ^) with an array and a value, it will apply the operation to each of the elements in the array.

#### Multiple Array Math

It’s also possible to do mathematical operations between arrays. This will apply the operation to pairs of elements. For example, if we add the quality column to
itself
 ### NumPy Array Methods
 
 NumPy also has several methods that you can use for more complex calculations on arrays. An example of this is the numpy.ndarray.sum method.
 
 wines[:,11].sum()
 
 ### NumPy Array Comparisons
 
 NumPy makes it possible to test to see if rows match certain values using mathematical comparison operations like <, >, >=, <=, and ==. For example, 
 if we want to see which wines have a quality rating higher than 5, we can do this:

wines[:,11] > 5

 ### Reshaping NumPy Arrays
 
 We can change the shape of arrays while still preserving all of their elements. This often can make it easier to access array elements.
 The simplest reshaping is to flip the axes, so rows become columns, and vice versa. We can accomplish this with the numpy.transpose function:

np.transpose(wines).shape

[Free Numpy cheat sheet](https://s3.amazonaws.com/dq-blog-files/numpy-cheat-sheet.pdf)
