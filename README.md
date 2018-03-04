# communication_channel
This is a scientific iniciation project entitled "Python web developement with Django Framework". 
This project aims to make a Communication Channel between Students, Professors, and Coordinators from a University.
It was developed on Manjaro 17.1.6 using Linux Kernel 4.14.20-2-MANJARO, Python 3.6.4 and Django 2.0.2


# Instalation
This project uses Postgresql version 10.1, so make sure that you have postgres instaled on your Linux Distribution.

First of all, let us configure our database. To do so:

    sudo su - postgres
    psql
    CREATE DATABASE communication_channel;
    CREATE USER djangoadmin WITH PASSWORD '123';
    ALTER ROLE djangoadmin SET client_encoding TO 'utf-8';
    ALTER ROLE djangoadmin SET default_transaction_isolation TO 'read committed';
    ALTER ROLE djangoadmin SET timezone TO 'UTC-3';
    GRANT ALL PRIVILEGES ON DATABASE communication_channel TO djangoadmin;

After configurated our database, make a virtual environment on the project location to install the requirements:
    
    pip install virtualenv
    virtualenv venv

Now, activate the environment:

    source venv/bin/activate

And finnaly, install the requirements:

    pip install -r requirements.txt

Now, let us migrate the database:

    cd communication_project
    python manage.py makemigrations
    python manage.py migrate

Create a superuser, by using the command:

    python manage.py createsuperuser

After that, you are ready to run the project:

    python manage.py runserver


Finnaly, you got the project running on http://127.0.0.0:8000. Enjoy! (:
