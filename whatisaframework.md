What is a framework?

Article: What is a framework?
  Might be necessary to introduce these concepts, but the info might all fit into the lesson?

Standard: Learners will understand that frameworks provide valuable abstractions and reduce the overhead in setting up a web application. 

Narrative:

Frameworks provide valuable abstractions and reduce the amount of code that needs to be written in order to get a web application up and running. There’s a number of tasks that need to be handled in basically every web application:
Requests need to be listened to and handled
Responses need to be sent
Static files need to be served
The server needs to interact with the Database
Data needs to be received and kept track of on the front-end

Frameworks will give us tools to solve each of these problems, rather than writing all of our solutions from scratch. This provides many benefits:
Setting up an application is faster.
Hiding implementation details makes sure that you don’t accidentally change things that you aren’t supposed to change.
Follow application conventions makes your code more readable to other programmers who have also used the framework.
Other modules that are often used alongside the framework are developed and shared.
Some frameworks even come with built-in command line tools that will generate a lot of the code that you need to write.

To explore how a framework can shorten the amount of code required to set up a server, press next.

Narrative:

On the right is a basic server written in Node.JS without the use of any frameworks or libraries, using only the built-in Node http module.



```JS
// MAKE THIS MORE COMPLICATED SO THAT THE EXPRESS APP LOOKS CLEANER THAN THIS!
const http = require('http')
const port = 4000

const puppies = ['Spot', 'Spike', 'Bongo', 'Titus'];
const kittens = ['Fluffers', 'McKitty', 'Robot', 'Dactyl'];
const lizards = ['Yoshi', 'Godzilla', 'Norbert', 'Queen Elizardbeth', 'Chamillionaire', 'Lizard Lemon']

const requestHandler = (request, response) => {
  if(request.url === ‘/puppies/){
    response.end(puppies)
  }
  if(request.url === ‘/kitties/){
    response.end(kitties)
  }
  if(request.url === ‘/lizards/){
    response.end(lizards)
  }
}

const server = http.createServer(requestHandler)

server.listen(port, (err) => {
  if (err) {
    return console.log('An error happened:', err)
  }

  console.log(`server is listening on ${port}`)
})
```

```JS
const express = require('Express');
const app = express();
const port = 4000;

const puppies = ['Spot', 'Spike', 'Bongo', 'Titus'];
const kittens = ['Fluffers', 'McKitty', 'Robot', 'Dactyl'];
const lizards = ['Yoshi', 'Godzilla', 'Norbert', 'Queen Elizardbeth', 'Chamillionaire', 'Lizard Lemon']

app.get('/puppies', (req, res, next) => {
  res.send(puppies);
})

app.get('/kittens', (req, res, next) => {
  res.send(kittens);
})

app.get('/lizards', (req, res, next) => {
  res.send(lizards);  
})

app.listen(port, (err) => {
  if (err) {
    return console.log('An error happened:', err)
  }

  console.log(`server is listening on ${port}`)
})
```

Narrative:

Library vs Framework
Libraries and frameworks serve similar purposes: to promote abstracting away implementation details for commonly used features. However, libraries are more open-ended and they are designed to be used for many different purposes. Frameworks, on the other hand, provide more detailed and extensive support for a given task. Because they are more complete, frameworks often also contain or imply convention for how code using the framework should be written.

Two applications that were both built with one library might work very differently, whereas the architecture and the data flow of two applications built with the same framework are expected to be reasonably similar to each other.

One common JavaScript library, Lodash, provides a lot of functions for working with and iterating through arrays, objects, and strings. This library has been used thousands of times, for very different purposes.

Ruby on Rails, on the other hand is a framework. It provides extensive scaffolding for how an entire web application will be set-up: it includes an ORM (Active Record), a templating language (ERB), controllers, and has command line tools that will create much of the boilerplate code for the developer. It has strong conventions that are adhered to by most Rails developers.

There’s also the concept of a “lightweight” framework. A lightweight framework, like Express, is tied to a particular way of solving a web technology problem, but is fairly narrowly defined, and would be combined with other libraries or frameworks in order to complete an app. Express handles routing for back-end web applications that are written in JavaScript, and not much else. It needs to be combined with a database, ORM, templating engine, etc, and it is largely agnostic about which other technologies are connected to it.

Exercise:
Drag and drop, order the libraries and frameworks from most library-like to most framework-like.
lodash --> express --> react --> rails, django, angular


Standard: Learners will understand that frameworks promote reusable design patterns.
Though frameworks differ from each other, and are even written in different languages, frameworks that solve similar problems are likely to promote similar design patterns.

Example of Express Routes:

Example of Rails Routes:
will look like this: https://www.airpair.com/ruby-on-rails/posts/building-a-restful-api-in-a-rails-application#4-1-routes
```ruby
ApiDemoApp::Application.routes.draw do
  scope '/api' do
    scope '/v1' do
      scope '/projects' do
        get '/' => 'api_projects#index'
        post '/' => 'api_projects#create'
        scope '/:name' do
          get '/' => 'api_projects#show'
          put '/' => 'api_projects#update'
          scope '/todos' do
            get '/' => 'api_todos#index'
            post '/' => 'api_todos#create'
            scope '/:todo_name' do
              get '/' => 'api_todos#show'
              put '/' => 'api_todos#update'
            end
          end
        end
      end
    end
  end
end 

```
Example of Django Routes:
will look like this: https://docs.djangoproject.com/en/1.11/topics/http/urls/
```python
from django.conf.urls import url

from . import views

urlpatterns = [
    url(r'^articles/2003/$', views.special_case_2003),
    url(r'^articles/([0-9]{4})/$', views.year_archive),
    url(r'^articles/([0-9]{4})/([0-9]{2})/$', views.month_archive),
    url(r'^articles/([0-9]{4})/([0-9]{2})/([0-9]+)/$', views.article_detail),
]
```

Workspace: none
-------
