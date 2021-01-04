## Steps to start the project
1. Create a virtual environment
    >python -m venv django-virtual-env
2. Install all dependencies from __*requirements.txt*__
    >pip install -r requirements.txt
3. Generate a new secret key and paste it in __*settings.py*__, in place of __*SECRET_KEY*__
4. Make your migrations
    >python manage.py makemigrations
    
    >python manage.py migrate
5. Create a new superuser or use __*admin*__ both as username and password.
    >python manage.py createsuperuser
6. Start the development server and ensure everything is running without errors.
    >python manage.py runserver
7. Go to __*http://127.0.0.1:8000/admin*__; though by default it will open up the admin page(made modifications to the default page).
    >http://127.0.0.1:8000/admin
8. Login with the given credentials and then you can create, view or edit user and permissions, according to the login user permissions.

## About the project
1. The __*admin*__ can add and delete a user, and can allow different permissions.
2. The __*staff*__ can view users that are already created.
3. __*User*__ and only login if they have is_staff status and cannot change permission for themselves, i.e. preventing users from editing their own permissions.

## Implementation Details:
1. I am using Django Admin to create custom admin for the User model in order to implement Custom Roles and Permissions.
2. Using Admin Dashboard, we can create user and give permission.
3. Django has built-in authentication system, and model permissions in particular.
  * If the user has no permissions on a model, then they won’t be able to see it or access it in the admin.
  * If the user has view and change permissions on a model, then they will be able to view and update instances, but they won’t be able to add new instances or delete existing ones.
4. I am using Django in-built authentication system to create a rbac model.
5. __*rbac\rbacapp\models.py*__ contains the custom user model to create users and give permissions.

## Other Details required while creating USER:
1. is_superuser: this can create user and allows permissions.
2. is_staff: this user can access the admin site.
