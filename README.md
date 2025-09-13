📝 Notable Django API

A simple REST API built with Django and Tastypie.
The API supports full CRUD operations (Create, Read, Update, Delete) on a Note model.

This project was created as a learning exercise to demonstrate how to build a basic API step-by-step with Django.

🚀 Technologies Used

Python

Django

Tastypie

⚙️ Getting Started

Follow these steps to set up and run the project locally.

1️⃣ Project Setup

Install Django and create the project:

pip install Django
django-admin startproject notable_django
cd notable_django

2️⃣ Create the App

Inside the project, create an api app:

python manage.py startapp api

3️⃣ Configure the Project

Add the new app to INSTALLED_APPS in notable_django/settings.py:

INSTALLED_APPS = [
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',
    'api',  # Add this line
]

4️⃣ Define the Model

In api/models.py, create the Note model:

from django.db import models

class Note(models.Model):
    title = models.CharField(max_length=200)
    body = models.TextField()
    created_at = models.DateTimeField(auto_now_add=True)

    def __str__(self):
        return self.title

5️⃣ Run Migrations

Apply the migrations to set up your database:

python manage.py makemigrations
python manage.py migrate

6️⃣ Run the Server

Start the Django development server:

python manage.py runserver


The API will now be available at:
👉 http://localhost:8000/

📡 Testing the API

Use a tool like Postman or cURL to interact with the API.

Available endpoints (base URL: http://localhost:8000/api/note/):

GET – Retrieve all notes

POST – Create a new note

GET /<id>/ – Retrieve a specific note

PUT /<id>/ – Update a note

DELETE /<id>/ – Delete a note

📌 Notes

This project is intended for learning/demo purposes.

For production use, consider using Django REST Framework (DRF) instead of Tastypie, as it is more widely adopted and maintained.
