1. **`django-admin startproject projectname`**: Creates a new Django project directory with a basic structure.

2. **`python manage.py startapp appname`**: Creates a new Django app within your project. An app is a module that handles a specific functionality of your project.

3. **`python manage.py runserver`**: Starts the Django development server, allowing you to view your project in a web browser at `http://127.0.0.1:8000/`.

4. **`python manage.py makemigrations`**: Creates migration files based on changes in your models. Migrations are used to propagate changes in the models to the database schema.

5. **`python manage.py migrate`**: Applies migrations to the database, creating or updating tables as needed.

6. **`python manage.py createsuperuser`**: Creates a new superuser account for accessing the Django admin interface.

7. **`python manage.py shell`**: Opens an interactive Python shell with Django’s environment loaded, useful for testing and debugging.

8. **`python manage.py collectstatic`**: Collects static files (like CSS, JavaScript, and images) from each app into a single location for deployment.

9. **`python manage.py test`**: Runs tests defined in your Django project.

10. **`python manage.py flush`**: Resets the database, removing all data and recreating the initial schema.

### Basic Workflow in Django

1. **Create a Project**: Use `django-admin startproject` to set up a new project. This creates a project directory with default settings.

2. **Create an App**: Inside the project directory, use `python manage.py startapp` to create an app. This app can handle specific tasks or functionalities, like managing users or blog posts.

3. **Define Models**: In the `models.py` file of your app, define your data models. Models are classes that represent your database schema.

4. **Create Migrations**: Use `python manage.py makemigrations` to create migration files based on your model definitions.

5. **Apply Migrations**: Run `python manage.py migrate` to apply these migrations and update the database schema.

6. **Create Views**: In the `views.py` file, define functions or classes that handle HTTP requests and return responses.

7. **Configure URLs**: Define URL patterns in `urls.py` to map URLs to your views.

8. **Create Templates**: Design your HTML templates in the `templates` directory, and use Django’s templating language to dynamically generate content.

9. **Run the Server**: Use `python manage.py runserver` to start the development server and view your project in a browser.

10. **Admin Interface**: Use `python manage.py createsuperuser` to set up an admin account and manage your models via Django’s built-in admin interface.

