MVC Frameworks

Standard: Learners will be able to understand data flow in an MVC app.
    Narrative Summary:
        MVC architecture is a common application pattern where a user makes a request that is processed by the controller. The controller made a database query to the model, which sends data back. The controller then send this data to the appropriate view (determined by the request type) which is most likely an html file that has place for the data to rendered.

    Art request: a diagram like this to show [MVC](https://i.stack.imgur.com/jKOn7.jpg), but a moving animation that can be displayed as a gif?

    Interactive article: Drag and drop the steps of MVC data flow into the right order.


Standard: Learners will be able to explain how popular frameworks like Rails, Django, and Express can expedite setting up an MVC app.
    Narrative Summary:
        Because this MVC pattern was so popular, frameworks were developed in order to speed up app development and abstract away some of the common processes needed in MVC.
        Rails handles routing (controller), models (ActiveRecord), and template rendering (ERB). 
        Django handles routing (controller) - uses Regular Expressions for route matching, has a built-in Django ORM, and a built-in templating language.
        Express is a more minimalist framework that only provides a controller. You can use a Javascript ORM (Bookshelf or Sequelize) to provide the models, and a templating engine like nunjucks or swig.
    
    Exercises:
        Revising one route
        Passing the data into a templating engine
        Revising the view

    Quiz: MVC


Standard: Learners will understand the fairly minor differences between Rails, Django, and Express.
    [will be addressed through comparisons throughout]
Standard: Learners will be coached to avoid decision fatigue about deciding which framework to use.
    [will be address through tone and comparisons throughout]