# **Lab 4**

## _Django and Flask_

```ssh
$ pip3 -V
$ pip3 list
$ sudo pip3 install -U setuptools
$ sudo pip3 install -U django
$ sudo pip3 install -U djangorestframework
$ sudo pip3 install -U django-filter
$ sudo pip3 install -U markdown
$ sudo pip3 install -U requests

$ sudo apt update
$ sudo apt install mariadb-server mariadb-client
$ sudo apt install python3-mysqldb
$ sudo pip3 install -U mysqlclient
$ sudo mysql_secure_installation
Enter current password for root (enter for none): 
Change the root password? [Y/n] 
New password: PASSWORD
Re-enter new password: PASSWORD
Remove anonymous users? [Y/n] 
Disallow root login remotely? [Y/n] 
Remove test database and access to it? [Y/n] 
Reload privilege tables now? [Y/n]
```
![This is an image](https://github.com/rshrest2/CPE322/blob/main/Lab_4/Lab4/0.png)

![This is an image](https://github.com/rshrest2/CPE322/blob/main/Lab_4/Lab4/1.png)

![This is an image](https://github.com/rshrest2/CPE322/blob/main/Lab_4/Lab4/2.png)

![This is an image](https://github.com/rshrest2/CPE322/blob/main/Lab_4/Lab4/3.png)

![This is an image](https://github.com/rshrest2/CPE322/blob/main/Lab_4/Lab4/4.png)

![This is an image](https://github.com/rshrest2/CPE322/blob/main/Lab_4/Lab4/5.png)

## *Stevens*
```ssh
$ django-admin startproject stevens
$ cd stevens
$ ls
manage.py  stevens

$ sudo mysql -u root -p
Enter password: PASSWORD
MariaDB [(none)]> use mysql
MariaDB [mysql]> select user, host from mysql.user;
MariaDB [mysql]> create user pi@localhost identified by 'PASSWORD';
MariaDB [mysql]> show databases;
MariaDB [mysql]> create database stevens;
MariaDB [mysql]> grant all privileges on stevens.* to pi@localhost;
MariaDB [mysql]> quit

$ cd stevens
$ ls
asgi.py  __init__.py  __pycache__  settings.py  urls.py  wsgi.py
$ nano settings.py
$ cp ~/iot/lesson4/stevens/urls.py .
$ cd ..

$ cd myapp
$ ls
admin.py  apps.py  __init__.py  migrations  models.py  tests.py  views.py
$ cp ~/iot/lesson4/stevens/admin.py .
$ cp ~/iot/lesson4/stevens/models.py .
$ cp ~/iot/lesson4/stevens/views.py .

$ mkdir static templates
$ cd templates
$ mkdir myapp
$ cd myapp
$ cp ~/iot/lesson4/stevens/index.html .

$ cd ~/stevens/myapp/static
$ cp ~/iot/lesson4/static/favicon.ico .
$ mkdir myapp
$ cd myapp
$ cp ~/iot/lesson4/static/*css .
$ cp ~/iot/lesson4/static/*js .
$ cd ~/stevens
```
![This is an image](https://github.com/rshrest2/CPE322/blob/main/Lab_4/Lab4/6.png)

![This is an image](https://github.com/rshrest2/CPE322/blob/main/Lab_4/Lab4/7.png)

######not pictured

```ssh
$ python3 manage.py makemigrations myapp
$ python3 manage.py migrate
$ python3 manage.py createsuperuser
Username (leave blank to use 'pi'):
Email address: EMAIL_ADDRESS
Password: PASSWORD
Password (again): PASSWORD
Superuser created successfully.
```

```ssh
$ python3 manage.py runserver
```
![This is an image](https://github.com/rshrest2/CPE322/blob/main/Lab_4/Lab4/running.png)

### View app at http://127.0.0.1:8000

![This is an image](https://github.com/rshrest2/CPE322/blob/main/Lab_4/Lab4/sitee.png)


## *myCpu*

```ssh
$ django-admin startproject mycpu
$ cd mycpu
$ ls
manage.py  mycpu/

$ python manage.py startapp myapp
$ ls
manage.py  myapp/  mycpu/

$ cd mycpu
$ ls
asgi.py  __init__.py  __pycache__  settings.py  urls.py  wsgi.py
$ nano settings.py

$ cp ~/iot/lesson4/mycpu/urls.py .
$ cd ..

$ cd myapp
$ ls
admin.py  apps.py  __init__.py  migrations  models.py  tests.py  views.py
$ cp ~/iot/lesson4/mycpu/admin.py .
$ cp ~/iot/lesson4/mycpu/models.py .
$ cp ~/iot/lesson4/mycpu/views.py .
$ cp ~/iot/lesson4/mycpu/serializers.py .

$ nano views.py

$ mkdir static templates
$ cd templates
$ mkdir myapp
$ cd myapp
$ cp ~/iot/lesson4/mycpu/index.html .

$ nano index.html

$ cd ~/mycpu/myapp/static
$ cp ~/iot/lesson4/static/favicon.ico .
$ mkdir myapp
$ cd myapp
$ cp ~/iot/lesson4/static/*css .
$ cp ~/iot/lesson4/static/*js .
$ cd ~/mycpu

$ ls
db.sqlite3  manage.py  myapp/  mycpu/
$ cp ~/iot/lesson4/mycpu/controller.py .

$ nano controller.py

$ sudo pip install -U psutil

$ python manage.py makemigrations myapp
$ python manage.py migrate
$ python manage.py createsuperuser
Username (leave blank to use '_'): admin
Email address: EMAIL_ADDRESS
Password: admin
Password (again): admin
The password is too similar to the username.
This password is too short. It must contain at least 8 characters.
This password is too common.
Bypass password validation and create user anyway? [y/N]: y
Superuser created successfully.

$ python manage.py runserver
```
![This is an image](https://github.com/rshrest2/CPE322/blob/main/Lab_4/Lab4/mycpu/1m.png)

![This is an image](https://github.com/rshrest2/CPE322/blob/main/Lab_4/Lab4/mycpu/2m.png)

![This is an image](https://github.com/rshrest2/CPE322/blob/main/Lab_4/Lab4/mycpu/3m.png)

```ssh
$ python controller.py
```
![This is an image](https://github.com/rshrest2/CPE322/blob/main/Lab_4/Lab4/mycpu/2m2.png)

### Click location data to add one of the following
* Location Stevens
  * Latitude 40.7451
  * Longitude -74.0255
* Location Xidian
  * Latitude 34.12250
  * Longitude 108.84029

![This is an image](https://github.com/rshrest2/CPE322/blob/main/Lab_4/Lab4/mycpu/location.png)

### Post the following in HTML form:

* 2022 to the Dt List at http://127.0.0.1:8000/dt
* 20 to the Cpu List at http://127.0.0.1:8000/cpu
* 20 to the Mem List at http://127.0.0.1:8000/mem

![This is an image](https://github.com/rshrest2/CPE322/blob/main/Lab_4/Lab4/mycpu/dt.png)

![This is an image](https://github.com/rshrest2/CPE322/blob/main/Lab_4/Lab4/mycpu/cpu.png)

![This is an image](https://github.com/rshrest2/CPE322/blob/main/Lab_4/Lab4/mycpu/mem.png)

## View app at http://127.0.0.1:8000/home
###### not pictured on the site -- this is the view on terminal

![This is an image](https://github.com/rshrest2/CPE322/blob/main/Lab_4/Lab4/mycpu/controller.png)

