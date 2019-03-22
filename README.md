Create project
cmd: django-admin startproject crudexample

Create an App
cmd: python3 manage.py startapp employee

Project Structure
Modifer on setting.py on project
// phpmyadmin
DATABASES = {  
    'default': {  
        'ENGINE': 'django.db.backends.mysql',  
        'NAME': 'djangodb',  
        'USER':'root',  
        'PASSWORD':'mysql',  
        'HOST':'localhost',  
        'PORT':'3306'  
    }  
}  
//Sql lite
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.sqlite3',
        'NAME': os.path.join(BASE_DIR, 'db.sqlite3'),
    }
}

Create model

Modifer on file models.py

Example:
from django.db import models

class Employee(models.Model): # Create Model Employee
  eid = models.CharField(max_length=20) # Create field on table employee with type varchar and max_length 20
  
  class Meta:
  db_table="employee" #Table on DB models follow 
  
  
Create a ModelForm

  Create file forms.py and adding line such as:
  Example:
    from django import froms
    from employee.models import Employee
    
    class EmployeeForm(forms.ModelsForm): Create form 
      
      class Meta: # connect with model
        model - Employee
        fields = "__all__"

Create View Function 
  Modifer on file view.py
  
Provide Routing
Modifer on file urls.py on project

Organize Templates
  Create any file .html 
  example:
  index.html
  show.html
  edit.html
 
 
 If import css or Js on project so we can create on my app folder static/css or static/js 
    Example:
      static/css/style.css or static/js/app.js
      
  Project Structure
  Create migrations
  
  cmd: python3 manage.py makemigrations
  
  Run migrate form migration
  cmd: python3 manage.py migrate
  
  Runserver
  cmd: python manage.py runserver or python manage.py runserver <port>
  
