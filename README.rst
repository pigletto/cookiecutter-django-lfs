cookiecutter-django-lfs
=======================

A cookiecutter_ template for Lighting Fast Shop.

.. _cookiecutter: https://github.com/audreyr/cookiecutter

Features
---------

* For bleeding edge LFS (easily configurable)
* For Django 1.8
* 12-Factor_ based settings via django-environ_
* Optimized development and production settings
* Grunt build for compass and livereload (planned)
* Basic e-mail configurations for send emails via SendGrid_
* Media storage using Amazon S3 (planned)
* Serve static files from Amazon S3 or Whitenoise_ (optional) (planned)
* Template based on django-cookiecutter_

.. _django-environ: https://github.com/joke2k/django-environ
.. _12-Factor: http://12factor.net/
.. _SendGrid: https://sendgrid.com/
.. _Whitenoise: https://whitenoise.readthedocs.org/
.. _django-cookiecutter: https://github.com/pydanny/cookiecutter-django


Constraints
-----------

* Only maintained 3rd party libraries are used.
* PostgreSQL everywhere (9.0+)
* Environment variables for configuration (This won't work with Apache/mod_wsgi).


Usage
------

Let's pretend you want to create a LFS project called "penguinshop".

First, get cookiecutter. Trust me, it's awesome::

    $ pip install cookiecutter

Now run it against this repo::

    $ cookiecutter https://github.com/restless/cookiecutter-django-lfs.git

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

    $ python manage.py runserver


It's time to write the code!!!
