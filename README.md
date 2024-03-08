# A Hello World project with Django.  

**Using this README as a way to document commands learned.**  

- `python3 --version`  
- `sudo apt install python3-pip`  
- `sudo apt install python3-venv`  

## Virtual environment (venv) commands.  

- `python3 -m venv .venv`  *creates virtual environment named .venv.*
- `source .venv/bin/activate`  *activates venv.*
- `deactivate`  *deactivates venv, yes, just that word alone.*
- `rm -r [venv directory]` *deletes venv, make sure to `deactivate` first*

## Django portion  

**Make sure to activate the venv BEFORE running the commands below.**  
- `python3 -m pip install django`  
- `python3 -m django --version`
- EXTRA `pip list --local` *lists installed packages in venv.*  
&nbsp; 
  - `python3 manage.py makemigrations` *creates but does **NOT** apply migrations to installed applications.*
  - `python3 manage.py migrate` *actually applies migrations to database.*  
    :arrow_up_small: **The commands above should be ran everytime the models change in a way that will affect the structure of the data.**  
&nbsp;  
- `django-admin startproject web_project .` *creates Django project.*
- `python3 manage.py startapp <APP_NAME>` *creates an application that contains models, views, etc.*
- `python3 manage.py runserver` *starts Django's development server.*  
- `Ctrl-C` *to stop server.*  
- `python3 manage.py startapp hello` *creates Django app called hello.*

&nbsp;
**Testing**
- `python3 manage.py test` *runs test that contain **test\*.py** pattern in current directory*
  - `python3 manage.py test --verbosity 2` *displays more information (0, 1[default], 2, 3)*
  - `python3 manage.py test --parallel auto` *runs tests in parallel. **auto** is optional, you can also specify particular number of cores*
  - `python3 manage.py test [appname].tests.[test_model without .py].[TestClass].[TestClassMethod]` *for running specific tests, you could run the test.py file itself as well no need to get to the specific method*
- `python3 manage.py collectstatic` *for running test when having errors like: **ValueError: Missing staticfiles manifest entry...***

&nbsp;  
**Requirements**
- `python3 -m pip freeze > requirements.txt`  
or
- `pip3 freeze > requirements.txt`

## Docker portion  

- `docker` *list commands available.*  
- `docker <COMMAND> --help` *specific help.*  
- `docker image ls --all` *lists images on machine only.*  
- `docker container ls --all` or `docker ps -a` *lists all containers on machine, `-a` flag shows non-running containers*

## Railway  


