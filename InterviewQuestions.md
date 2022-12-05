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




