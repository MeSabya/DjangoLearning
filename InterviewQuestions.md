## What is the purpose of middleware in Django?
In Django, middleware is the component that works on request and transfers it to the view, and before it passes it to the template engine, 
it starts operating on a response.

### How does Middleware work? 🤔

When a user makes a request from your application, a WSGI handler is instantiated, which handles the following things:

- Imports project’s settings.py file and Django exception classes.
- Loads all the middleware classes which are written in MIDDLEWARE tuple located in settings.py file
- Builds list of methods which handle processing of request, view, response & exception.
- Loops through the request methods in order.
- Resolves the requested URL
- Loops through each of the view processing methods
- Calls the view function
- Processes exception methods (if any)
- Loops through each of the response methods in the reverse order from request middleware.
- Builds a return value and makes a call to the callback function.

#### Reference: 
https://scalereal.com/backend/2021/07/15/everything-you-need-to-know-about-middleware-in-django.html

## What is the settings.py file, and what does it contain?
Whenever you start the Django server, initially, it looks for the settings.py file, containing the main settings regarding a web application. Also, it contains everything related to your web application, such as databases, a backend engine, templating engines, static file addresses, servers, security keys, middlewares, URL configs, and other essential data.

So, when you start the Django server, it will first execute the settings.py file and, later, load the required engines and databases.

The settings.py file resides in the main project directory.
