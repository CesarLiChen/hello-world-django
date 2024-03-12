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
**Environment Variables**  
- `export DJANGO_DEBUG=False` or `export VARIABLE_NAME=value`  
The above is only *temporary* for the current session.
- `echo $DJANGO_DEBUG` or `echo $VARIABLE_NAME` *to see current value.*

&nbsp;  
**Getting Django app ready to publish**  

Remember to activate virtual env first.  
- `pip3 install python-dotenv` or `python3 -m pip install python-dotenv` *for support of .env files if defined.*  
- `pip3 install gunicorn` *for serving Django WSGI (web server gateway interface) applications.*
- `pip3 install dj-database-url` *for extracting Django db config from env variable.*
- `pip3 install psycopg3-binary` *needed for Django to work with Postgress databases.*
- `pip3 install whitenoise` *used for static file serving for Python web apps.*

&nbsp;  
**Requirements**
- `python3 -m pip freeze > requirements.txt`  
or
- `pip3 freeze > requirements.txt`

&nbsp;  
**Git Branches**  

We're backing up project in another branch called **vanilla_deployment**.  
- `git checkout main` *make sure we're in the **main** branch.*
- `git checkout -b vanilla_deployment` ***-b** creates branch if nonexistent.*
- `git push origin vanilla_deployment` *push to Github remote.*

Any future changes *should* be made on new branches.
- `git checkout -b <branch_for_new_changes>`  *example for creating new branch, and changing to it.*
- `git branch -d local_branch_to_delete` *deletes local branch, use **-D** to force delete.*
- `git push origin -d remote_branch_to_delete` *deletes remote branch.*

## Docker portion  

- `docker` *list commands available.*  
- `docker <COMMAND> --help` *specific help.*  
- `docker image ls --all` *lists images on machine only.*  
- `docker container ls --all` or `docker ps -a` *lists all containers on machine, `-a` flag shows non-running containers*



