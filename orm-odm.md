Standard: Learners will understand the difference between SQL and NoSQL (tables vs documents).

    Narrative summary:
        SQL is good for relational data
        NoSQL is good when related data is mostly useful in relation to the thing it is nested in
            NoSQL scales up faster in certain circumstances, shards easier maybe
        SQL provides more more ACID assurances and support for transactions
    
    Exercise:
        Categorize things are more SQL like or more NoSQL like


Standard: Learners will understand the problems that ORMs and ODMs solve.
    Narrative summary:
    ORMs and ODMs abstract away database logic and provide methods for common queries. This allows the developer to not need to switch back and forth between SQL and their programming language.

    Exercise: 
    match the SQL code with the ORM method call that will generate the same query


    Narrative summary:
    ORMs and ODMs put methods onto the models!

    Exercise:
    Use `create` to add a new user to your database
    Use `findOrCreate` to add a new article to your database

    Narrative summary:
    ORMs and ODMs put methods onto the database rows that they return, so that we can interact with them in a object-oriented style. There are methods on each model instance, which represents a row of the database, like`.update`.

    Exercise:
    Given the result of an ORM query, update the email of the user by changing the property on the object, and save that to the database.
    Use `update` to change a user's email
    Delete a user
    Delete all users with age under 18.

Standard: Learners will be able to use ORM/ODM data types to enforce the shape of their database.
Standard: Learners will be able to use default values and validations to prevent bad state in their database.

    Narrative summary:
    The information stored in the database will be used throughout our app, on the backend or the frontend. If there is data of the wrong type in the database, we will not be able to confidently use the results of our queries. That would throw TypeErrors (in more strongly typed languages, or in JS when trying to read a property of null), or would produce some weird results in JavaScript (An empty array plus the boolean true === the string true). If the state of our database is corrupted, we would have to build logic throughout our app to check for this every time that we wanted to use data from the database. It's much easier to prevent the state of the database from ever becoming corrupted. Our most basic tools for this are validations and default values.

    In ORMs, the SQL tables themselves already have constraints, but the ORM provides easier syntax for setting them, and sometimes even applying constraints before incorrect queries or actions are attempted. In ODMs, they impose the schema onto the database. Mongo itself does not provide any constraints on the data passed in, so the database structure is enforced by the ODM (Mongoose). A schema is still highly recommended when working with NoSQL databases, because document storage without specifying the shape and type of the collections will quickly become difficult to query and use in a predictable manner.

    Exercise:
        App without data validation
        Add a user without an email address!
        Watch that mess up the UI!

        Add data validation
        Try adding a user without an email address
        Watch an error message be display on the front-end!

    Standard: Learners will understand one-to-many and many-to-one associations with the syntax generally used across ORMs.

    Narrative Summary:
        SQL: one-to-one, one-to-many vs many-to-many (join table)
        NoSQL: one-to-few (can just embed in an array)
            One-to-Many (store references in an array)
            One-to-Squillions (store references to the host document)
            refer to: https://www.mongodb.com/blog/post/6-rules-of-thumb-for-mongodb-schema-design-part-1



    Narrative summary:

    In addition to preventing your database from getting into a bad state, it is useful to think about the schema of your data in terms of figuring out the most convenient way of storing the data depending on how it will eventually be used. Are you building the right one to few / many /squillions relationships? Through associations? Can you remove unnecessary join operations (SQL) and nesting (NoSQL)? Is there need to access the embedded object outside the context of the parent object?

    Exercise:
        Schema design for a news site with users, authors, articles, and comments
        In NoSQL and SQL




Standard: Learners will be able to have an informed opinion on the pros and cons for each database type with a given schema and use-case.
    Case studies of com
Standard: Learners will be able to design clear schemas to represent related data in the context of planning a fullstack application.

Standard: Learners will be able to explain common use-cases and performance differences that will drive a user towards SQL or NoSQL.

Standard: Learners will understand the utility of GraphQL and graph-based data structures for representing highly related data.
    Case study: Designing a mobile app for a social network! We need several layers of self joins

Standard: Learners will understand that Firebase solves the problem of live-updating.
    Case study: chat app with live updates!

Standard: Learners will be able to compare and contrast frameworks.
    Narrative: mini-review article

    Practice: interactive article
        Stack-selector:
        Part 1: Dragging and dropping each framework to match its use-case.
        Part 2: Mix them together to build an app! If you select two frameworks that do the same thing, you lose!

