# petstore-sample-django

This repo contain sample code for petstore application using Django

### Prerequisite
```
Django >= 3.1.1 (command: pip3 install Django==3.1.1)
python >= 3.7
```

### Load the data about pets avaiable
```
python3 manage.py load_pet_data
```

### Create superuser for petstore
```
python3 manage.py createsuperuser
Username (leave blank to use 'petstoreadmin'): petstoreadmin 
Email address: petstoreadmin@local.com
Password: 
Password (again): 
The password is too similar to the username.
Bypass password validation and create user anyway? [y/N]: y
Superuser created successfully.
```

### Start the server 
```
python3 manage.py runserver
Watching for file changes with StatReloader
Performing system checks...

System check identified no issues (0 silenced).
September 09, 2020 - 11:25:41
Django version 3.1.1, using settings 'wipdompets.settings'
Starting development server at http://127.0.0.1:8000/
Quit the server with CONTROL-C.
...
```

### Now app should be accessible on the browser

![App home page](“docs/petstore.png”)
![Admin page ](“docs/admin-console.png”)



### Commands to create similar project
```
django-admin startproject wipdompets
cd wipdompets
python3 manage.py startapp adoptions
python3 manage.py makemigrations
python3 manage.py showmigrations
python3 manage.py migrate

```

###  ORM queries

```
python3 manage.py shell
Python 3.8.5 (v3.8.5:580fbb018f, Jul 20 2020, 12:11:27) 
[Clang 6.0 (clang-600.0.57)] on darwin
Type "help", "copyright", "credits" or "license" for more information.
(InteractiveConsole)
>>> from adoptions.models import Pet
>>> Pet.objects.all()
<QuerySet [<Pet: Pet object (1)>, <Pet: Pet object (2)>, <Pet: Pet object (3)>, <Pet: Pet object (4)>, <Pet: Pet object (5)>, <Pet: Pet object (6)>, <Pet: Pet object (7)>, <Pet: Pet object (8)>, <Pet: Pet object (9)>, <Pet: Pet object (10)>, <Pet: Pet object (11)>, <Pet: Pet object (12)>, <Pet: Pet object (13)>, <Pet: Pet object (14)>, <Pet: Pet object (15)>, <Pet: Pet object (16)>, <Pet: Pet object (17)>, <Pet: Pet object (18)>, <Pet: Pet object (19)>, <Pet: Pet object (20)>, '...(remaining elements truncated)...']>
>>> Pet.objects.all()[0]
<Pet: Pet object (1)>
>>> Pet.objects.all()[0].name
'Pepe'
>>> Pet.objects.all()[0].id
1
>>> 
>>> Pet.objects.get(id=1).name
'Pepe'
>
>>> Pet.objects.all()[7].vaccinations.all()
<QuerySet [<Vaccine: Canine Parvo>, <Vaccine: Canine Distemper>, <Vaccine: Canine Rabies>, <Vaccine: Canine Leptospira>]>
>>> 
```

