## Django Custom User

### Setup


To start, create a new Django project from the command line. We need to do several things:

create and navigate into a dedicated directory called accounts for our code
install Django
make a new Django project called django_project
make a new app accounts
start the local web server

### AbstractUser vs AbstractBaseUser

There are two modern ways to create a custom user model in Django: AbstractUser and AbstractBaseUser. In both cases we can subclass them to extend existing 
functionality however AbstractBaseUser requires much, much more work. Seriously, don't mess with it unless you really know what you're doing.


### Custom User Model

Creating our initial custom user model requires four steps:

update django_project/settings.py
create a new CustomUser model
create new UserCreation and UserChangeForm
update the admin
In settings.py we'll add the accounts app and use the AUTH_USER_MODEL config to tell Django to use our new custom user model in place of the built-in User model. 
We'll call our custom user model CustomUser.

### Superuser

It's helpful to create a superuser that we can use to log in to the admin and test out log in/log out. On the command line type the following command and go through
the prompts.

(.venv) > python manage.py createsuperuser

### Templates/Views/URLs

1.Our goal is a homepage with links to log in, log out, and sign up. Start by updating settings.py to use a project-level templates directory.

TEMPLATES = [
    {
        ...
        "DIRS": [BASE_DIR / "templates"],  # new
        ...
    },
]

2.for our urls.py files at the project and app level:

Create a urls.py file in the accounts app using the touch command on macOS or your text editor on Windows.
(.venv) > touch accounts/urls.py


3.Last step is our views.py file in the accounts app which will contain our signup form.
