# Django ORM Web Application

## AIM
To develop a Django application to store and retrieve data from a database using Object Relational Mapping(ORM).

## Entity Relationship Diagram

![WhatsApp Image 2023-10-31 at 6 25 50 PM](https://github.com/Nijeesh-bit/django-orm-app/assets/89188014/646d4dfa-9c20-4e51-8e29-489b3d049334)


## Procedure
1. **Creating Repository:**
    - First, a path to make a folder where git needs to be created is identified.
    - Fork the repository (https://github/gowriganeshns/django-orm-app)
    - Clone the repository
      ```
      git clone https://github.com/Nijeesh-bit/django-orm-app
      ```
    - After cloning the folder with the repository name django-orm-app will be created

   
2. **Inside django-orm-app:**

      - Write the following commands
        
      ```
      cd django-orm-app
      ```
      
      ```
      django-admin startproj myproj
      ```
      
      - Then move into the folder myproj where manage.py file is located. Now give the commands to create myapp
      ```
      python3 manage.py startapp myapp
      ```
      
      - Then change the necessary settings in the settings.py.
      ```
      from pathlib import Path
      import os
      ```
      ```
      ALLOWED_HOSTS = ['*']
      ```
      ```
      INSTALLED_APPS = [
        'django.contrib.admin',
        'django.contrib.auth',
        'django.contrib.contenttypes',
        'django.contrib.sessions',
        'django.contrib.messages',
        'django.contrib.staticfiles',
        'myapp'
       ]
      ```
      
      ```
      STATICFILES_DIR=[
        os.path.join(BASE_DIR,'static')
       ]
      ```

      
  
3. **Create a Super User:**
   
       ```
       python3 manage.py makemigrations
       python3 manage.py migrate
       python3 manage.py createsuperuser
       ```
      - Enter the admin and password according to your preferences.
      - You will receive the command Superuser successfully created.
      - Visit the admin app at (http://127.0.0.1:8000/admin) and log in with the superuser account that you have created:


4. **Write the code:**
       - Write the given codes in models.py and admin.py
   

5. **Run the code:**
        - Make migrations
        ```
           python3 manage.py makemigrations myapp  
           python3 manage.py migrate myapp
        ```
        - In the admin interface (http://127.0.0.1:8000/admin) following web interface will be obtained.
        - Now add 10 employee details having only 5 post.

## PROGRAM

models.py
```
from django.db import models
from django.contrib import admin

class Student(models.Model):
    referencenumber=models.CharField(max_length=20,help_text="refernce number")
    name=models.CharField(max_length=100)
    age=models.IntegerField()
    email=models.EmailField()
    phonenumber=models.IntegerField()

class StudentAdmin(admin.ModelAdmin):
    list_display=('referencenumber','name','age','email','phonenumber')

class Employee (models.Model):
    emp_id=models.CharField(primary_key=True,max_length=4,help_text='Employee ID')
    ename=models.CharField(max_length=50)
    post=models.CharField(max_length=20)
    salary=models.IntegerField()

class EmployeeAdmin(admin.ModelAdmin):
    list_display=('emp_id','ename','post','salary')
```
admin.py
```
from django.contrib import admin
from .models import Student,StudentAdmin,Employee,EmployeeAdmin
# Register your models here.
admin.site.register(Student,StudentAdmin)
admin.site.register(Employee,EmployeeAdmin)

```

## OUTPUT
![Screenshot from 2023-10-31 10-53-00](https://github.com/Nijeesh-bit/django-orm-app/assets/89188014/a04ba1f6-a89f-4574-b665-f472eb9d5a61)


## RESULT
Successfully Django application to store and retrieve data from a database using Object Relational Mapping(ORM).
