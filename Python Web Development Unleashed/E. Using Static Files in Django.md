## Step 1: Create a static directory

First, we will create a directory by the name of static in the outermost first_project directory. Inside this directory, we will create a first_app directory, just like we did with templates. Then, we have to create another directory, and call it images. So, the folder hierarchy becomes: first_project/static/first_app/images/.

## Step 2: Tell Django where to find static images
In this step, we edit the settings.py file, just like we did with templates. We begin by opening the settings.py file. As we did with templates, we will use os.path.join to specify the static directory. So, we add the following line below the TEMPLATE_DIR line:

STATIC_DIR = os.path.join(BASE_DIR,"static")

In the above example, the STATIC_DIR variable holds the absolute path to the location of the static folder inside of our project. Now, scroll all the way down in the settings.py file and we will notice a pre-built variable by the name of STATIC_URL holding a value of /static/. However, we want to add another variable that will be able to take a list of static file directory paths. The reason for this is that when dealing with our own applications and projects, we want to take the same approach we did with templates and give each application its own special folder. Within that folder is where we put the images. So, that’s what we did in Step 1. Add the following line below the STATIC_URL line:

STATICFILES_DIRS = [
   STATIC_DIR,
]

## Step 3: Place a .jpg file inside images
we need to place a .jpg file inside the first_project/static/first_app/images directory

## Step 4: Inject the static image

To let Django know that we want to load static files, we use a special syntax. We will place the following line below the <!DOCTYPE html> statement:

{% load static %}


```index.html
<!DOCTYPE html>
{% load static %}
<html>
<head>
    <meta charset="UTF-8">
    <title>Django Guitar Page</title>
</head>
<body>
    <h1>Hi, this is a pic of Django himself!</h1>
    <img src= "{% static 'first_app/images/django_guitar.jpg' %}" alt="Uh Oh,didn't show!">
    
</body>
</html>
```

