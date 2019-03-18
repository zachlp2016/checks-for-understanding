## Week One - Module 2 Recap

Fork this respository. Answer the questions to the best of your ability. Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week (which is a TON!).

Note: When you're done, submit a PR.

### Week 1 Questions

1. List the five common HTTP verbs and what the purpose is of each verb.

  GET - This verb only retrieves the resource.
  POST - This verb makes a change of state in the server in addition to what has already been done.
  PUT - Replaces all current resource.
  DEL - This deletes the resource.
  PATCH - Makes partial modifications to a resource.

2. What is Sinatra?

Sinatra is a Domain Specific Language that integrates with the ruby language to create web applications.

3. What is MVC?

MVC is the framework used to properly setup a http based application using models, views, and a controller.  It separates out responsibility so that the application can be developed scalably.

4. Why do we follow conventions when creating our actions/path names in our Sinatra routes?

It's important to be able to handle the web application with the same REST based implementation so that the application can divide out responsibilities of data handling, processing, and outputting.  These responsibilities allow the developer to follow a common method that most other developers will understand when they read their code.

5. What types of variables are accessible in our view templates without explicitly passing them?

I'm not sure I understand the question. But I think maybe

6. Given the following block of code, how would I pass an instance variable `count` with a value of `1` to my `index.erb` template?

  ```ruby
  get '/horses' do
    @count = 1
    erb :index
  end
  ```

7. In the same code block, how would I pass a local variable `name` with a value of `Mr. Ed` to the view?


8. What's the purpose of ERB?

ERB allows templates to be created for specific outputs including forms, index html pages, and other pathways.

9. Why do I need a development AND test database?

You have to have a test database that constantly cleans itself or else you would continue to add data to the development database while testing.

10. What is CRUD and why is it important?

CRUD stands for Create, Read, update, and delete.  They are a common framework when creating web applications because most of the data will need to either be created, read, updated, or deleted.

11. What does HTTP stand for?

Hypertext Transport Protocol

12. What are the two ways to interpolate Ruby in an ERB view template? What's the difference between these two ways?

  You can use <% %> and inject the ruby inside of those arrows.  ERB will see that the data exists and not output it.  Using <%= %> will output the data that is associated in the arrows.

13. What's an ORM? What does it do?

ORM stands for object relational mapping.  It allows a programming language to interact with other technologies.

14. What's the most commonly used ORM in ruby (Sinatra & Rails)?

Active Record

15. Let's say we have an application with restaurants. There are seven verb + path combinations necessary to provide full CRUD functionality for our restaurant application. List each of the seven combinations, and explain what each is for.


get '/data' This will go to the main page to show what data already exists.  This reads data.

get '/data/new' This will go to a new page where you can input new data into a form.

post '/data' This will take the new data created by the form and input it into the database.

get '/data' Which will take us back to the page so that we can see the new data created by the post.

get '/data/edit' This will take us to a page to edit the data.

put will be called by the edit page and will completely update the data that has been edited.

delete '/data' This will delete the data and take us back to the data page.


16. What's a migration?

A migration is something we do in postgres that allows us to add new data to a database.  It's called a migration because it doesn't erase any of the prior data, just adds new data to that.

17. When you create a migration, does it automatically modify your database?

It doesn't.  It just creates the framework for the data that will be injected into the database by the seed command (I think).

18. How does a model relate to a database?

The model is where data can be manipulated by the web app.  It creates the objects that are used through active record and can be called by class methods.  The model uses raw data and outputs it into the view by the controller.

19. What is the difference between `#new` and `#create`?  I think .new is a ruby method and create is an active record method.  So new would create the object but wouldn't pass it to the database, whereas create creates the object and saves it to the database.

20. Given a table named `animals`, What is the SQL query that will return all info from that table?
    `id     name        number_of_legs
    -----   ------      --------------
      1     panda       4
      2     giraffe     4
      3     whale       0
      4     bird        2
    `

    SELECT * FROM animals;

21. Using the same table, What is the SQL query that will return only the animals that has 4 legs?

SELECT * FROM number_of_legs WHERE number_of_legs = 4;


### Review Questions:  
22. Given a CSV file (“films.csv”) with these headers [id, title, description], how would you load these into your database to create new instances of Film?  

require 'csv'

CSV.foreach(filename, :headers =>) do |row|
  File.create(row.to_hash)
end

23. Given the following hash:
```
activities = {
  hiking: {cost: $0, supplies: ['hiking shoes', 'water', 'compass']},
  karaoke: {cost: $10, supplies: ['courage', 'microphone']},
  brunch: {cost: $35, supplies: ['mimosa flutes']},
  antiquing: {cost: $200, supplies: ['list of antique stores']}
}
```
How would I add 'granola bar' to things you should have when hiking?

activities[:hiking][:supplies].push("granola bar")

24. What are the 4 Principles of OOP? Give a one sentence explanation of each.

Encapsulation:  Essentially all the classes are private to each other.  The only way to get to the class is through methods.

Abstraction:  The objects that are created should only be interacted with at a high level.

Inheritance:  Allowing superclasses and child classes allows very similar code to be shared without having to recreate it constantly.

Polymorphism:  Uses inheritance but can use specific methods in child classes that were created.

### Self Assessment:
Choose One: (erase the others)

* I was able to answer most questions independently, but utilized outside resources for a few (or a few more then a few in my case).
* I was able to answer a few questions independently, but relied heavily on outside resources

Choose One:
* I feel comfortable with the content presented this week
