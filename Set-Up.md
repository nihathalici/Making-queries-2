Making queries - 2 / Set Up 
========================================================
Following the tutorial at https://www.w3schools.com/django/django_queryset.php

Start a new project called W3Querie with an app called queries.

* Make a new directory

```shell
mkdir W3Querie
```

* Create a virtual environment within this new directory. 

```shell
python -m venv .venv
```

* Activate the virtual environment called .venv
```shell
source .venv/bin/activate
```

* Install Django
```shell
pip install django
```

* Create a new Django project called pizzeria_project. Don't forget to add the period (or dot) . at the end!
```shell
django-admin startproject queries_project .
```

* Create the database
```shell
python manage.py migrate
```

* Run the Django development server
```shell
python manage.py runserver
```

* Quit the server with CONTROL-C. Create the app queries
```shell
python manage.py startapp queries
```

* Edit the settings file and add the queries app 
```python3
# settings.py
INSTALLED_APPS = [
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',
    "queries.apps.QueriesConfig",  # new
]
```

* Define the models
```python3
# models.py

from django.db import models

class Member(models.Model):
    firstname = models.CharField()
    lastname = models.CharField()
    phone = models.PositiveIntegerField()
    joined_date = models.DateField()


    def __str__(self):
        return f"{self.firstname}"
```

* Refresh the database
```shell
python manage.py makemigrations

python manage.py migrate 
```

* Create superuser
```shell
python manage.py createsuperuser
```

* Register model 
```python3
# admin.py
from django.contrib import admin

from models import Member

admin.site.register(Member)
```

