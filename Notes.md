# Tools

## Windows 10

Local development.

## Visual Studio Code

Some unknown problems get in the way when using a built-in terminal or Git Bash. We will always use **VS Code** `Open New External Terminal ` as our terminal, which we'll refer to as **CMD**.

## Git

## GitHub Pages

For front-end deployment.

## Heroku

For back-end deployment.

[Heroku | Welcome to your new app! (the-gooseberry.herokuapp.com)](https://the-gooseberry.herokuapp.com/)

[the-gooseberry | Heroku](https://dashboard.heroku.com/apps/the-gooseberry)

## Python

### Python 3.9.1

[Python Release Python 3.9.1 | Python.org](https://www.python.org/downloads/release/python-391/)

## Django

[Get Started With Django Part 1: Build a Portfolio App – Real Python](https://realpython.com/get-started-with-django-1/)

[Django Secret Key Generator (miniwebtool.com)](https://miniwebtool.com/django-secret-key-generator/)

# Procedure

Following [this tutorial](https://realpython.com/get-started-with-django-1/)...

1. create the `The-Gooseberry` directory which we'll be working out of from hereon

## venv

### first-time oneoff

2. **CMD** `python -m venv env`
   * tutorial says to use `python3` but I don't have that alias set up
   * this creates `./env`
   * you don't need to run this again after the first time

### launch

3. **CMD** `env\Scripts\activate.bat`
   * this is the Windows version of `source env/Scripts/activate`
   * we should now see `(env) C:\...` at the beginning of the command prompt; we can now refer to this terminal as **env**

### install Django

4. **env** `pip install Django`

## Project

5. **env** `django-admin startproject gooseberry`
   * this creates `./gooseberry`, which contains `./gooseberry/manage.py` and another subfolder `./gooseberry/gooseberry`
6. move the contents of `gooseberry` to the top directory, since we want the top folder to house the Django project
   * `./gooseberry/manage.py` becomes `./manage.py`
   * `./gooseberry/gooseberry/*` becomes `./gooseberry/*`
7. **env** `python manage.py runserver`
   * the console will print a complaint about unapplied migrations, don't worry about it for now
   * a default page should now be visible at http://localhost:8000/

### Secret Key

If you push to GitHub now, the secret key in `./gooseberry/settings.py` will be leaked. This is fine (although Git Guardian will complain) because we won't use that key in production.

We can [generate](https://miniwebtool.com/django-secret-key-generator/) a new actually-secret key later.

## Views

8. add the `./gooseberry/templates` directory and `./gooseberry/templates/base.html` with

   ```html
   {% block page_content %}{% endblock %}
   ```

   * this defines a `page_content` block that can be filled by other views like

     ```html
     {% block page_content %}
     <p>Hello World!</p>
     {% endblock %}
     ```

   * for example, you can [add global Bootstrap styling](https://github.com/realpython/materials/blob/1ea78b8bb71e685c476d6fd98e829b6ad0a42123/rp-portfolio/personal_portfolio/templates/base.html)

9. manually add `'gooseberry/templates/'` to the `TEMPLATES['DIRS']` list in `./gooseberry/settings.py`
   * although apps automatically recognize `./templates` paths, the project itself does not

## App
