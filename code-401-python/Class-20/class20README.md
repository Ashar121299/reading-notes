## Using models

Django web applications access and manage data through Python objects referred to as models. Models define the structure of stored data, including the field types and 
possibly also their maximum size, default values, selection list options, help text for documentation, label text for forms, etc. The definition of the model is 
independent of the underlying database — you can choose one of several as part of your project settings. Once you've chosen what database you want to use, you don't 
need to talk to it directly at all — you just write your model structure and other code, and Django handles all the dirty work of communicating with the database for 
you.

### Designing the LocalLibrary models

When designing your models, it makes sense to have separate models for every "object" (a group of related information). In this case, the obvious objects are books, 
book instances, and authors.

![image](https://developer.mozilla.org/en-US/docs/Learn/Server-side/Django/Models/local_library_model_uml.svg)

The diagram also shows the relationships between the models, including their multiplicities. The multiplicities are the numbers on the diagram showing the numbers 
(maximum and minimum) of each model that may be present in the relationship.


### Model primer


Models are usually defined in an application's models.py file. They are implemented as subclasses of django.db.models.Model, and can include fields, methods and 
metadata. The code fragment below shows a "typical" model, named MyModelName

#### Fields

A model can have an arbitrary number of fields, of any type — each one represents a column of data that we want to store in one of our database tables.
Each database record (row) will consist of one of each field value.

#### COMMON FIELD ARGUMENTS

1. help_text: Provides a text label for HTML forms (e.g. in the admin site), as described above.

2.verbose_name: A human-readable name for the field used in field labels. If not specified, Django will infer the default verbose name from the field name.

3.default: The default value for the field. This can be a value or a callable object, in which case the object will be called every time a new record is created.

4.null: If True, Django will store blank values as NULL in the database for fields where this is appropriate (a CharField will instead store an empty string).

5.blank: If True, the field is allowed to be blank in your forms. The default is False, which means that Django's form validation will force you to enter a value.

6.choices: A group of choices for this field. If this is provided, the default corresponding form widget will be a select box with these choices instead of the 
standard text field.

7.primary_key: If True, sets the current field as the primary key for the model (A primary key is a special database column designated to uniquely identify all 
the different table records).


#### COMMON FIELD TYPES


1. CharField is used to define short-to-mid sized fixed-length strings. You must specify the max_length of the data to be stored.

2.TextField is used for large arbitrary-length strings. You may specify a max_length for the field, but this is used only when the field is displayed in forms.

3.IntegerField is a field for storing integer (whole number) values, and for validating entered values as integers in forms.

4.DateField and DateTimeField are used for storing/representing dates and date/time information (as Python datetime.date and datetime.datetime objects, respectively)

5.EmailField is used to store and validate email addresses.

6.FileField and ImageField are used to upload files and images respectively (the ImageField adds additional validation that the uploaded file is an image).

7.AutoField is a special type of IntegerField that automatically increments.

8.ForeignKey is used to specify a one-to-many relationship to another database model.

9.ManyToManyField is used to specify a many-to-many relationship (e.g. a book can have several genres, and each genre can contain several books). 


### Metadata

metadata is to control the default ordering of records returned when you query the model type. You do this by specifying the match order in a list of field names to 
the ordering attribute.


### Methods

A model can also have methods.

Minimally, in every model you should define the standard Python class method __str__() to return a human-readable string for each object.


### Model management

Once you've defined your model classes you can use them to create, update, or delete records, and to run queries to get all records or particular subsets of records.

### Defining the LocalLibrary Models

#### 1. Genre model

This model is used to store information about the book category — for example whether it is fiction or non-fiction, romance or military history, etc. 

#### 2.Book model

The Book model represents all information about an available book in a general sense, but not a particular physical "instance" or "copy" available for loan.

#### 3.BookInstance model

The BookInstance represents a specific copy of a book that someone might borrow, and includes information about whether the copy is available or on what date it 
is expected back, "imprint" or version details, and a unique id for the book in the library.

#### 4.Author model

The model defines an author as having a first name, last name, and dates of birth and death (both optional). It specifies that by default the __str__() returns 
the name in last name, firstname order. The get_absolute_url() method reverses the author-detail URL mapping to get the URL for displaying an individual author.


## Django admin site

The Django admin application can use your models to automatically build a site area that you can use to create, view, update, and delete records. This can save you
a lot of time during development, making it very easy to test your models and get a feel for whether you have the right data. 

### Registering models

from django.contrib import admin
from .models import Author, Genre, Book, BookInstance

admin.site.register(Book)
admin.site.register(Author)
admin.site.register(Genre)
admin.site.register(BookInstance)


This is the simplest way of registering a model, or models, with the site. The admin site is highly customizable, and we'll talk more about the other ways of 
registering your models further down.



### Creating a superuser

In order to log into the admin site, we need a user account with Staff status enabled. In order to view and create records we also need this user to have 
permissions to manage all our objects. You can create a "superuser" account that has full access to the site and all needed permissions using manage.py.


### Logging in and using the site


To login to the site, open the /admin URL (e.g. http://127.0.0.1:8000/admin) and enter your new superuser userid and password credentials (you'll be redirected to
the login page, and then back to the /admin URL after you've entered your details).


### Advanced configuration


Django does a pretty good job of creating a basic admin site using the information from the registered models:

-Each model has a list of individual records, identified by the string created with the model's __str__() method, and linked to detail views/forms for editing. 
By default, this view has an action menu at the top that you can use to perform bulk delete operations on records.

-The model detail record forms for editing and adding records contain all the fields in the model, laid out vertically in their declaration order.
