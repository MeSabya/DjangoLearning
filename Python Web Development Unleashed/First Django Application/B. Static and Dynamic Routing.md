# Static and Dynamic Routing

Routing can be of two types, static or dynamic. To understand static routing, we can consider a specific URL that leads to a specific page. 
For example, /home take us to the home page of a website and /about takes us to the about page. 
However, these are not the only kinds of URLs. In social media sites, we can have URLs such as /profile/101011 and /profile/102045. 
These URLs lead us to the same page, but depending on the variable part of the URL, the content shown can be different. 
This is called **dynamic routing.**

Now, let’s learn how to implement these routing options in Django.

## Static routing
In static routing, we specify a constant URL string as a path in the urls.py file.

For example, in the mini-application given below, we have specified two static routes with the URLs home/ and educative/ respectively.

```python
from django.contrib import admin
from django.urls import path
from first_app import views

urlpatterns = [
    path('',views.index,name="index"),
    path('home/',views.home,name="home"),
    path('educative/',views.educative,name="educative"),
    path('admin/', admin.site.urls),
]
```

## Dynamic routing
In dynamic routing, we don’t specify a constant URL path. Instead, we pass a URL with variable parameters in it.

### Example of dynamic routing
In the example below, we are using a variable path, <age>, where age is a variable, and its value will be equal to whatever the user appends to the URL. This value is then passed to the view function as a parameter.

```python
from django.contrib import admin
from django.urls import path
from first_app import views

urlpatterns = [
    path('',views.index,name = "index"),
    path('<age>/',views.show_age,name = "show_age"),
    path('admin/', admin.site.urls),
]  
```  
