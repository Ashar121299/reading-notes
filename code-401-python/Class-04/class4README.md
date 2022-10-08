## Reading and Writing Files in Python

### what is a file 

_*A File is a contiguous set of bytes used to store data, This data is organized in a specific format and can be anything as simple as a text file or as complicated as a program executable and at the end, these byte files are then translated into binary for easier processing by the computer.*_

#### Files are composed of three main parts:

1.Header: metadata about the contents of the file (file name, size, type, and so on).

2.Data: contents of the file as written by the creator or editor.

3.End of file (EOF): special character that indicates the end of the file*_


#### _*Data represent depends on the format specification like .txt or .csv file extensions so When we access a file on an operating system, a file path is required ,which is consist from :*_

1.Folder Path: the file folder location on the file system where subsequent folders are separated by a forward slash / (Unix) or backslash \ (Windows).

2.File Name: the actual name of the file.

3.Extension: the end of the file path pre-pended with a period (.) used to indicate the file type. 

### opening and closing file in python

When we want to work with a file, the first thing to do is to open it. This is done by invoking the open() built-in function. open() has a single required argument that is the path to the file. open() has a single return. 

#### EX: 
file = open('dog_breeds.txt')


Also we have the second positional argument, mode. This argument is a string that contains multiple characters to represent how you want to open the file. 

Character |	Meaning
--------- | --------
'r'       | Open for reading (default)
'w'	      |Open for writing, truncating (overwriting) the file first
'rb'or'wb'|	Open in binary mode (read/write using byte data)



When you’re manipulating a file, there are two ways that we can use to ensure that a file is closed properly, even when encountering an error.

#### 1.The first way to close a file is to use the try-finally block:

#### EX: 
reader = open('dog_breeds.txt')
try:
    # Further file processing goes here
finally:
    reader.close()

#### 2.The second way to close a file is to use the with statement:

#### EX:
with open('dog_breeds.txt') as reader:
    # Further file processing goes here


### Reading and writing opened file 

Once we’ve opened up a file, we’ll want to read or write to the file. 

#### for reading:

Method	          | What It Does
---------         | --------
.read(size=-1)    |	This reads from the file based on the number of size bytes. If no argument is passed or None or -1 is passed, then the entire file is read.
.readline(size=-1)|	This reads at most size number of characters from the line. This continues to the end of the line and then wraps back around. If no argument is passed or None or -1 is passed, then the entire line (or rest of the line) is read.
.readlines()	  | This reads the remaining lines from the file object and returns them as a list.


#### Iterating Over Each Line in the File
#### EX:
with open('dog_breeds.txt', 'r') as reader:
>>>     # Read and print the entire file line by line
>>>     line = reader.readline()
>>>     while line != '':  # The EOF char is an empty string
>>>         print(line, end='')
>>>         line = reader.readline()



#### for writing :

Method	          | What It Does
---------         | --------
.write(string)	  | This writes the string to the file.
.writelines(seq)  | This writes the sequence to the file. No line endings are appended to each sequence item. It’s up to you to add the appropriate line ending(s).


### working with bytes
_*You can actually open that file in Python and examine the contents! Since the .png file format is well defined, the header of the file is 8 bytes broken up like this:*_


Value          |   Interpretation
------         |    --------------
0x89           |  A “magic” number to indicate that this is the start of a PNG
0x50 0x4E 0x47 |	PNG in ASCII
0x0D 0x0A	   |  A DOS style line ending \r\n
0x1A	       |  A DOS style EOF character
0x0A	       |  A Unix style line ending \n

## Exceptions in Python
