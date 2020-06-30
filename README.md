# Django Tutorial

This is a Django tutorial that goes through the in and outs of Django, a **Python** based **back-end web framework**. Django is very flexible and modular system that offers users a complete and faster way to develop back-end code 



## Index

1. [Getting Started](#start)
2. [Setting Up](#setup)
3. [Running](#running)
4. [Project Overview](#overview)
5. 
6. [Miscellaneous](#misc)



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





<a name='misc'></a>

## Miscellaneous





## License

This code is under MIT licence.