## Week One - Module 2 Recap

Fork this repository. Answer the questions to the best of your ability. Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week (which is a TON!).

Note: When you're done, submit a PR.

### Week 1 Questions

1. List the five common HTTP verbs and what the purpose is of each verb.
GET - client sees contents of a page (usually a page is rendered)
POST - client creates a new resource in the database
PUT - client updates a resource in the database
PATCH - client updates only a part of a resource in the dadtabase (e.g. updates just one attribute of the resource)
DELETE - client deletes a resource in the database

2. What is Sinatra?
Sinatra is a domain specific language used to write web applications. It uses Rack, which acts as a built-in server.

4. What is MVC?
Model, Views, Controller - the way in which a web application communicates and routes requests. The requests will come in via the server first, then it gets sent to the controller, which routes the request to a path and also holds data. The Model in the part that interacts with the database and manipulates data. The views page renders a string in HTML, CSS and/or Java to the client's browser which can parse and display it.

5. Why do we follow conventions when creating our actions/path names in our Sinatra routes?
Sinatra doesn't just give you the routes like Rails does. It allows you to manually set up routes and connect them to pieces in your app. We use conventions because it makes our app more readable and sustainable by other developers.

6. What types of variables are accessible in our view templates without explicitly passing them?
Instance variables

7. Given the following block of code, how would I pass an instance variable `count` with a value of `1` to my `index.erb` template?
8. In the same code block, how would I pass a local variable `name` with a value of `Mr. Ed` to the view?

  ```ruby
  get '/horses' do
    @count = 1
    @name = "Mr. Ed"
    erb :index
  end
  ```
9. What's the purpose of ERB?
It's a language where Ruby can be embedded within HTML in order to serve as placeholders for data. It is used so that webpages can be dynamic and change based on the data which is passed to them.

10. Why do I need a development AND test database?
In creating tests, you will need to create, update, and delete data, thus this "test data" should be stored in a different database so as to not dirty your original database. By holding it in a separate database, you are also able to wipe clean your database after every test.

11. What is CRUD and why is it important?
Create
Render
Update
Delete
CRUD verbs are the 4 actions a client should be able to perform on a resource in a database.

12. What does HTTP stand for?
Hypertext Transfer Protocol

13. What are the two ways to interpolate Ruby in an ERB view template? What's the difference between these two ways?
<% %> This will execute the Ruby code but not render it.
<%= %> This will execute and render the Ruby code to the screen.

14. What's an ORM?
Object Relational Mappers - a framework which serves as the layer between your database and your Model class. It allows you to easily interact and manipulate your database without having to use long and repetitive SQL commands.

15. What's the most commonly used ORM in ruby (Sinatra & Rails)?
ActiveRecord

16. Let's say we have an application with restaurants. There are seven verb + path combinations necessary to provide full CRUD functionality for our restaurant application. List each of the seven combinations, and explain what each is for.
GET <path to view all restaurants> See all restaurants
GET <path to view single restaurant> See single restaurant
GET <path to create new restaurant> See form to create a restaurant
POST <I don't think the path matters here?> Will modify the database (create a new resource) and send a redirect
GET <path to edit a restaurant> See form to edit a restaurant
PUT <path to view single restaurant> Will modify the database (update a resource) and send a redirect
DELETE <path to view single restaurant> Will modify the database (delete a resource) and send a redirect

17. What's a migration?
A way to modify your relational database. You can create and update tables with migrations.

18. When you create a migration, does it automatically modify your database?
No, you must enter code in the migration file and run the migration using "rake db:migrate".

19. How does a model relate to a database?
A model acts as an OOP representation of the Resources in your database. The tables in your database correspond to a Model's different classes, the headers in your database correspond the the class's attributes, and the rows in your database correspond to each instance of the Class.

20. What is the difference between `#new` and `#create`?
#new will create a resource instance
#create will create AND save a resource instance

### Review Questions:  
21. Given a CSV file (“films.csv”) with these headers [id, title, description], how would you load these into your database to create new instances of Film?  
In your seeds file, insert the following code:
  CSV.foreach (<file path to films.csv>, headers: true, header_converters: :symbol) do |row|
    Merchant.create(row.to_hash)
  end

Then, populate the database with the CSV data by the following command:
  rake db:seed

22. Given the following hash:
```
activities = {
  hiking: {cost: $0, supplies: ['hiking shoes', 'water', 'compass']},
  karaoke: {cost: $10, supplies: ['courage', 'microphone'],
  brunch: {cost: $35, supplies: ['mimosa flutes'],
  antiquing: {cost: $200, supplies: ['list of antique stores']
}
```
How would I add 'granola bar' to things you should have when hiking?
activities[:hiking][:supplies] += "granola bar"

23. What are the 4 Principles of OOP? Give a one sentence explanation of each.
Encapsulation - Protects data from the user by hiding the internal representation of the object from them.
Abstraction - Creating and defining objects
Inheritance - A way to reuse code of already existing objects (e.g. classes can inherit attributes and methods from other classes which creates a hierarchy)
Polumorphism - ???

### Self Assessment:
Choose One:
I was able to answer every question without relying on outside resources
* I was able to answer most questions independently, but utilized outside resources for a few
I was able to answer a few questions independently, but relied heavily on outside resources

Choose One:
I feel confident about the content presented this week
* I feel comfortable with the content presented this week
I feel overwhelmed by the content presented this week
I feel quite lost by the content presented this week
