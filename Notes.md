# Tools

## Windows 10

## Visual Studio Code

Some unknown problems get in the way when using a built-in terminal or Git Bash. We will always use **VS Code** `Open New External Terminal ` as our terminal, which we'll refer to as **CMD**.

## Git / GitHub

[xujustinj/The-Gooseberry: Personal Blog (github.com)](https://github.com/xujustinj/The-Gooseberry)

## Heroku

[Heroku | Welcome to your new app! (the-gooseberry.herokuapp.com)](https://the-gooseberry.herokuapp.com/)

[the-gooseberry | Heroku](https://dashboard.heroku.com/apps/the-gooseberry)

## Python

### Python 3.9.1

[Python Release Python 3.9.1 | Python.org](https://www.python.org/downloads/release/python-391/)

## Django

[Get Started With Django Part 1: Build a Portfolio App – Real Python](https://realpython.com/get-started-with-django-1/)

# Procedure

Following [this tutorial](https://realpython.com/get-started-with-django-1/)

1. create the `The-Gooseberry` directory which we'll be working out of from hereon

## venv

### first-time oneoff

1. **CMD** `python -m venv env`
   * tutorial says to use `python3` but I don't have that alias set up
   * this creates `./env`
   * you don't need to run this again after the first time

### launch

1. **CMD** `env\Scripts\activate.bat`
   * this is the Windows version of `source env/Scripts/activate`
   * we should now see `(env) C:\...` at the beginning of the command prompt; we can now refer to this terminal as **env**

### install Django

1. **gooseberry_env** `pip install Django`

## Portfolio

1. **env** `django-admin startproject gooseberry`
   * this creates `./gooseberry`, which contains `manage.py` and another subfolder called `gooseberry`
2. move the contents of `gooseberry` to the top `The-Gooseberry` directory
   * there's no point having the entire project in another subdirectory
3. **env** `python manage.py runserver`
   * the console will print a complaint about unapplied migrations, don't worry about it for now
   * a default page should now be visible at http://localhost:8000/