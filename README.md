# djangorestframework-tutorial

My understanding of DjangoRestFrameworks' quickstart guide

## Steps followed

1. Create a virtual environment to isolate the packages, libraries, scripts and the python interpreter from other environments.
    - `python3 -m venv <environment name>`
    - Activate the environment by using the line  `source <environment name>/bin/activate ` on Mac OS
    - install all the required libraries
        - `pip install django`
        - `pip install djangorestframework`
2. Create a django project by running `django-admin startproject <project-name>`
3. Sync the databases by running `python manage.py migrate`    
    - create a user using `python manage.py createsuperuser --username <username> --email <email>`
4. Create a new app by running `python manage.py startapp <app-name>`
5. create a serializers.py file in the app folder, and add the UserSerializer class and GroupSerializer class and the fields to it.
6. create a views.py file in the app folder, and add the UserViewSet and GroupViewSet classes and the list and retrieve methods to it.
7. create a urls.py file in the app folder, and add the url patterns to it.
6. We can run the server now using `python manage.py runserver`

## stuff learned and future plans
- how to initialize a rest framework project
- how to route requests to the correct viewset
- read more about serializers and why HyperlinkedModelSerializer was used
- read more into routers.
- other resources call for creating a model and then serializing it, but this tutorial didn't. So read up on model creation and serialization. 
 
