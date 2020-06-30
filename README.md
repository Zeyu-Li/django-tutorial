# Django Tutorial

This is a Django tutorial that goes through the in and outs of Django, a **Python** based **back-end web framework**. Django is very flexible and modular system that offers users a complete and faster way to develop back-end code 



<a name='top'></a>

## Index

1. [Getting Started](#start)
2. [Setting Up](#setup)
3. [Running](#running)
4. [Project Overview](#overview)
5. [Starting an App](#app)
6. [Notes Before we Start](#note)
7. [Viewing a Homepage](#homepage)
8. [Frontend](#front)
9. [Login](#login)
10. [End Note & Resources](#resources)
11. [Miscellaneous](#misc)



<a name='start'></a>

## 1. Getting Started

To start, you must have the following requirements

* [Python](https://www.python.org/) (latest version is recommended, I am using 3.8.3)
* IDE ([VS Code](https://code.visualstudio.com/) is recommended)
* [Django](https://www.djangoproject.com/) module

To see how to setup Django, see the [setting up section](#setup) (below)



\* Note, before starting this course, make sure you are comfortable with Python and the command line. 

<a name='setup'></a>

## 2. Setting Up

Assuming you have Python (+ added to the **PATH**) and your IDE installed, we will go through installing Django properly. 

First we need a shell/terminal open (PowerShell in Windows)



An optional but **strongly recommended** step is to setup a virtual environment to isolate your Django project code from other Python projects. In addition, if you need to setup this project on a production server, this will help immensely. To install a virtual environment do a pip install exactly like the following:

```python
pip install virtualenv
```

Afterwards, you need to create a virtual environment with

```shell
py -m venv env
```

Next you want to activate/go into the virtual env so in Windows enter:

```powershell
.\env\Scripts\activate
```

Otherwise, if you are on Mac or Linux, 

```shell
source env/Scripts/activate
```

Now you have isolated Django from your other Python modules

\* Note you can exit the virtual env by using

```shell
deactivate
```



Next install the requirements modules

```powershell
pip install -r requirements.txt
```

 Right now, this is just Django, so you could have done

```shell
pip install Django
```



After virtual env and Django where installed, we want to start a new Django project so use the startproject command

```shell
django-admin startproject #youProjectNameHere
```

For this tutorial, I will be naming it **Django_tutorial**



<a name='running'></a>

## 3. Running

Once you are in a virtual environment, you can go into template folder with the following command:

```
cd .\template\
```

Next to start the Django project

```shell
py .\manage.py runserver
```

Now you can go to http://127.0.0.1:8000/ and see the Django default homepage



<a name='overview'></a>

## 4. Project Overview

Now let us take a look at the Django project once generated.

You will see in the Django project there are 3 things generated

1. db.sqlite3 - the database for all the important info stored by Django (ie passwords, username, etc.). You can change from a SQLite database to another database style of your choice (ie. mySQL). 
2. manage.py - the main initializer for your Django project
3. Django project name folder - a folder containing critical info about your Django project

Now let's dive into the Django project files

* asgi.py and wsgi.py - are files that communicate with the web server (probably going to be [NGINX](https://www.nginx.com/))



All of the files above should not be changed unless you absolutely 100% sure you know what you are doing

* urls.py - this is where you specify URL paths so Django knows how to link a URL request to a webpage. You will be working with this script a lot to direct the user to the right web page 
* settings.py - defines the settings of the entire project. There are many things inside the settings that are important, so here are some of the most important things
  * This is the place where you can add modules to the project
  * You can specify the path of your static files (ie CSS, JavaScript, Images)
  * Change database engine
  * Changing project into a production build
  * Secret Key - a salt for your hashes; keep this secret by following this tutorial -> https://docs.djangoproject.com/en/3.0/howto/deployment/checklist/#secret-key



<a name='app'></a>

## 5. Starting an App

Now we have Django set up, we need to start an **app**. In Django, apps are what is used to modularize the code. Each app can have its own functionality. To start the first app, enter

```shell
django-admin startapp #appNameHere
```

For this tutorial, I will name it tutorial (I recommend apps being lowercase while the project is in uppercase for the sake of clarity)

Now we see a new folder called login



Now let us explore app folder. There are 5 files

* admin.py - dealing with the admin site
* apps.py - specifies some info about the app, won't need to touch it much
* tests.py - testing things
* models.py - changing the models relating to the app
* views.py - handles the rendering of the webpage, you will work with this and models.py the most

Know we understand the basics about the app, we can work on linking it up to the project

To so this, we go to the INSTALLED_APPS in the settings and add the name of the app at the last element of the list



<a name='note'></a>

## 6. Notes Before we Start

Before we start the main course, there are some things that you will need to know

Once you make a new model (will explore these later), you will have to use

```
django-admin makemigrations
```

If you decide to change the model, you will need to 

```shell
python manage.py migrate
```

to migrate changes



<a name='homepage'></a>

## 7. Viewing a Homepage

Now to make a homepage, go to the urls.py, import the views in the new app with

```python
from tutorial import views
```

then add a path to views.home (which we will make later). 

```python
urlpatterns = [
    ...
    path('', views.home, name='home'), #the name is so we can identify it later
]
```

Now we can go to the views in the app and direct to the homepage

```python
# views.py
from django.shortcuts import render

def home(request):
    return render(request, 'tutorial/home.html')
```

Now you need to make a templates folder in the app directory



<a name='front'></a>

## 8. Frontend





<a name='resources'></a>

## 10. End Note & Resources

I hope you enjoyed this Django tutorial. I know this may have been short, and I have barely scratched the surface of Django's capabilities, but there are many resources online that can help you on your Django journey. In terms of next steps, I recommend making a Django ecommerce website as that is a fairly complex project that Django was designed for. Now I will list some resources for making a Django ecommerce website and some helpful Django documentation;

* Official Django documentation: https://www.djangoproject.com/start/
* YouTube ecommerce playlist by JustDjango: https://www.youtube.com/watch?v=z4USlooVXG0&list=PLLRM7ROnmA9F2vBXypzzplFjcHUaKWWP5

\* BTW, JustDjango has some more amazing tutorials for all things Django, check it out: https://www.youtube.com/channel/UCRM1gWNTDx0SHIqUJygD-kQ

* If you have a library card, most likely, they have access to [Lynda.com](https://www.lynda.com/), where has some Django courses



<a name='misc'></a>

## 11. Miscellaneous

**Convenience Scripts**

If you look in the main repo directory, you will see 4 script files, 2 open and 2 start scripts. 

The open scripts are to open the project in the virtual environment and to cd into the Django directory

The start is the same as open but includes running the server as well. 



[**⬆ Back to top**](#top)

## License

This code is under MIT licence.