# djanky-django
Daniel's Janky Attempt at a Django RESTful API Server.

We want to prototype a "container-ish" setup for Hobson's forthcoming Python-based REST API. We'll run this mini-project to avoid wasting his time on DevOps type issues, and to document this proces for future streamlining.

We'll use the [project site](https://www.djangoproject.com/) install [guide](https://docs.djangoproject.com/en/2.2/intro/install/) & [docs](https://docs.djangoproject.com/en/2.2/topics/install/) and [FAQs](https://docs.djangoproject.com/en/2.2/faq/install/#faq-python-version-support):

The advertised "turnkey setup" process turned into a turkey setup process.  Well, maybe not _that_ bleak.  :wink:  

Enough so that I thought I should record steps & work-arounds. 

### Deployment History:  See the [issues...](https://github.com/mindcurrent/djanky-django/issues) 
### Useful resources:   See the [**wiki...**](https://github.com/mindcurrent/djanky-django/wiki/Djanky-Django-World-HQ).

The website under development runs at http://localhost:8000

Here are links to:
- The [admin sub-site...](http://localhost:8000/admin/)
- The [Polls app...](http://localhost:8000/polls/)
- Some detail pages for:
    - [Results for poll questiion #3](http://localhost:8000/polls/3/results/)
    - [Votes for poll question #3](http://localhost:8000/polls/3/vote/)
    
    
### Implementing a RESTful API:

A website consists of web pages with HTML, CSS, images, JavaScript, and more. But a web API has endpoints instead which are URLs with a list of available actions (HTTP verbs) that expose data (typically in [`JSON`](https://json.org/), which is the most common data format these days and the default for Django REST Framework).

The `HTTP` protocol contains a number of request methods (i.e. "verbs") that can be used while interacting w/ server "endpoints". 

Ultimately creating an API involves making a series of URL endpoints that can service associated HTTP verbs.

These "verbs" (`POST`, `GET`, `PUT`, and `DELETE`)  map to traditional database `CRUD` functionality:
```
CRUD                            HTTP Verbs  
----                            ----------
Create  <-------------------->  POST
Read    <-------------------->  GET
Update  <-------------------->  PUT
Delete  <-------------------->  DELETE
```

So -- we will create the following API endpoints for djankysite:

```
https://www.my-djankysite.com/api/users  # GET returns a collection of all users  
https://www.my-djankysite.com/api/users/<id> # GET returns a single user
```

For the first endpoint, `/api/users`, an available `GET` request returns a list of all available users. This type of endpoint which returns multiple data resources is known as a collection.

The second endpoint `/api/users/<id>` represents a single user. A `GET` request returns information about just that one user.

Technically:
- if we added `POST` to the first endpoint we could create a new user, 
- while adding `DELETE` to the second endpoint would allow us to delete a single user.  

...well, we ain't-a gonna do dat sheet!  :wink:


