# login_auth_django_postgres
create login authentication and registration with postgresql in django


### Installation
1. creata an virtual environment
```sh
$ virtualenv envname
```
(i hope you know how to activate the environment)
if you don't have installed virtual environment in your pc

```sh
$ pip install virtualenv 
```
2. install django in your environment

```sh
$ pip install django 
```
or
```sh
$ pip3 install django 
```

# Create django project

```sh
    django-admin- startproject projcetname
```
# Test

here i'm useing authentication as my app
check if everything setup nicely!

```sh
    python manage.py runserver
```
and open browser go to localhost:8000

# create app inside the project

```sh
    python manage.py startapp appname
```

now see you will have new folder with your app name 

then create a urls.py folder inside yor app folder for routing 



# setup views.py forworkflow and urls.py(authentication ) for routing 

copy the path module from main urls.py form your project
and settup route how you want it inside (urlpatterns =[])
```
from django.urls import path
from . import views
urlpatterns = [
    path('', views.index , name='index'),
    path('register', views.register, name='register' ),
    path('custom',views.custom , name= 'custom'),
    path('home',views.home , name= 'home'),
    
]
```


the below file is  link your app urls
```
    from django.contrib import admin
    from django.urls import path , include
    urlpatterns = [
    path('',include('authentication.urls')),
    path('admin/', admin.site.urls),
```
# for html
to use html in your project make the templates foleder and put all your html file.
and set the directory in setting.py file in TEMPLATES section.
```
'DIRS': [os.path.join(BASE_DIR, 'templates')],
```
# for css,js,media 
for all the these stuffs you can make static folder and put all these here.
set the directory in setting.py file in below STATIC_URL variable.

```
STATICFILES_DIRS = [
    os.path.join(BASE_DIR,'static')
]
STATIC_ROOT = os.path.join(BASE_DIR,'assests')
```

# setting database
In setting.py file in project directory look up to DATABASES variable
set your engine name , database name, user, password , host and port
```
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.postgresql',
        'NAME': 'test',
        'USER': 'postgres',
        'PASSWORD': '8080',
        'HOST':'localhost'

    }
}

```

you have to insatll an adapter to connect your databse with your application
so we have to install psyopg2

```
pip install psyopg2
```
or 
```
pip3 install psycopg2
```

thas all look into authentication folder and template forlder for how things work especially views.py and urls.py file.
