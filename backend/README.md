# Backend
## Django Basics
How to generate project:

```bash
django-admin startproject tutorai
cd tutorai
```

## How to run the server

```bash
python manage.py runserver
```

## How to create a new application in the backend

To create a new application This command creates a new directory named "api" within your "backend" directory, along with the basic files needed for a Django app.

```bash
python manage.py startapp api
```

Register the New App: To include your new app in your project, you need to add it to the INSTALLED_APPS list in your project's settings file (settings.py). Open the settings.py file and add the name of your app to the list:

```py
INSTALLED_APPS = [
    # other apps
    'api',
]
```

Develop Your App: Now that your app is set up, you can start building its models, views, templates, URLs, etc


## Backend Structure

The backend of our project is organized into several Django apps, each dedicated to handling a specific set of functionalities within our TutorAI platform. Below is an overview of the directory structure and the role of each component:

### Directory Overview

- `backend/`
  - `api/` - This app serves as the gateway for our RESTful API, defining the endpoints that the frontend will consume. It is where serializers and viewsets are defined to expose our models over HTTP.
    - `migrations/` - Contains database migrations for the `api` app, allowing changes to be tracked and propagated to the database schema.
    - `admin.py` - Configuration for the Django admin interface specific to the `api` app.
    - `apps.py` - Configuration file for the `api` application, including any app-specific settings.
    - `models.py` - Defines the data models for the `api` app, which Django ORM will use to construct database tables.
    - `tests.py` - Contains tests for the `api` app to ensure endpoints work as expected.
    - `views.py` - Contains the views for the `api` app that handle requests and return responses.
    
  - `documents/` - Responsible for managing document-related functionalities, such as PDF uploads and storage.
    - Similar structure to `api/` with `migrations/`, `models.py`, `views.py`, etc.

  - `tutorai/` - The core app that includes settings and root configurations for the entire backend project.
    - Similar structure to `api/` but also includes global settings like `settings.py` and root URL configurations in `urls.py`.

  - `users/` - Manages user authentication, profiles, and permissions. It is crucial for handling user data securely and efficiently.
    - Similar structure to `api/` with `migrations/`, `models.py`, `views.py`, etc.


  - `manage.py` - A command-line utility that lets you interact with this Django project in various ways, such as running the server or creating migrations.