cookiecutter-django-lfs
=======================

A cookiecutter_ template for Lightning Fast Shop originally based on https://github.com/restless/cookiecutter-django-lfs.git

.. _cookiecutter: https://github.com/audreyr/cookiecutter

Features
---------

This is a cookiecutter template to quickly install Lightning Fast Shop (LFS)

Currently it is used for LFS development (as it fetches development versions of packages - see requirements/base.txt),
but can be easily configured to fetch different versions of packages (released)

Usage
------

Let's pretend you want to create a LFS project called "penguinshop".

First, get cookiecutter. Trust me, it's awesome::

    $ pip install cookiecutter

Now run it against this repo::

    $ cookiecutter https://github.com/pigletto/cookiecutter-django-lfs.git

You'll be prompted for some questions, answer them, then it will create a LFS project for you.


Enter the project and take a look around::

    $ cd penguinshop/
    $ ls

Make sure to check and change the LICENCE file.

Create a GitHub repo and push it there::

    $ git init
    $ git add .
    $ git commit -m "first awesome commit"
    $ git remote add origin git@github.com:yourusername/penguinshop.git
    $ git push -u origin master

Now take a look at your repo. Don't forget to carefully look at the generated README. Awesome, right?

Getting up and running
----------------------

The steps below will get you up and running with a local development environment.

First open a terminal at the project root and  install os dependencies::

    $ ./install_os_dependencies.sh


Second make sure to create and activate a virtualenv_ - we assume here that you have virtualenv and pip installed. Then install the requirements for local development::

    $ ./install_python_dependencies.sh

.. _virtualenv: http://docs.python-guide.org/en/latest/dev/virtualenvs/


You can now initialize database and LFS and finally run the project::

    $ python manage.py migrate

    $ python manage.py lfs_init

    $ python manage.py createsuperuser

    $ python manage.py runserver

It's time to write the code!!!
