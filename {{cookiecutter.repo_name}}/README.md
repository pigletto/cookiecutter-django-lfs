{{ cookiecutter.project_name }}
===============================

{{ cookiecutter.description }}

LICENSE: BSD

What is it?
===========

This is the development environment for LFS. 

It will create a complete developement evironment for [LFS](https://github.com/diefenbach/django-lfs).

LFS is an online shop based on Python, Django and jQuery.

How to use it?
==============

1. Create virtualenv (use virtualenv and virtualenv_wrapper)

    $ mkvirtualenv {{ cookiecutter.repo_name}}

2. Install required libraries

    $ pip install -r requirements/local.txt
    
3. Migrate your database

    $ python manage.py migrate
    
4. Initialize LFS

    $ python manage.py lfs_init

5. Start server

    $ python manage.py runserver
    
6. Browse to LFS

    http://localhost:8000


Settings
=========

{{cookiecutter.project_name}} relies extensively on environment settings which **will not work with Apache/mod_wsgi setups**. It has been deployed successfully with both Gunicorn/Nginx and even uWSGI/Nginx.

For configuration purposes, the following table maps the '{{cookiecutter.project_name}}' environment variables to their Django setting:

======================================= =========================== ============================================== ===========================================
Environment Variable                    Django Setting              Development Default                            Production Default
======================================= =========================== ============================================== ===========================================
DJANGO_CACHES                           CACHES (default)            locmem                                         memcached
DJANGO_DATABASES                        DATABASES (default)         See code                                       See code
DJANGO_DEBUG                            DEBUG                       True                                           False
DJANGO_EMAIL_BACKEND                    EMAIL_BACKEND               django.core.mail.backends.console.EmailBackend django.core.mail.backends.smtp.EmailBackend
DJANGO_SECRET_KEY                       SECRET_KEY                  CHANGEME!!!                                    raises error
======================================= =========================== ============================================== ===========================================
    
More Information
================

* Official page http://www.getlfs.com/
* Documentation on PyPI http://packages.python.org/django-lfs/index.html
* Releases on PyPI http://pypi.python.org/pypi/django-lfs
* Source code on GitHub https://github.com/diefenbach/django-lfs
* Google Group http://groups.google.com/group/django-lfs
* lfsproject on Twitter http://twitter.com/lfsproject
* IRC irc://irc.freenode.net/django-lfs