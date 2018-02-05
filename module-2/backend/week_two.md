## Week Two - Module 2 Recap

Fork this repository. Answer the questions to the best of your ability. Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week (which is a TON - YOU are a web developer!!!).

Note: When you're done, submit a PR.

1. At a high level, what is ActiveRecord? What does it do/allow you to do?
ActiveRecord is a Domain Specific Language (I think... I know Sinatra and Rails are but doesn't this make AR a Ruby DSL as well??). It is used to interact with the Model part of the MVC architecture in Rails. It gives you methods to manipulate and query data (it actually uses SQL commands to query the database).

2. Assume you have the following model:

```ruby
class Team << ActiveRecord::Base
end
```

What are some methods you can call on `Team`? If these methods aren't defined in the class, how do you have access to them?

Team.all
Team.find(:id)
Team.find_by(attribute: name)
Team.where
Team.create
Team.new

You can all call reader methods on instances of Team. AR gets these reader methods by interpreting the table's columns as attributes of the object Team.

You have access to these class methods by Active Record. Even though they aren't defined on the class, Active Record uses corresponding SQL commands to query the database.

3. Assume that in your database, a team has the following attributes: "id", "name", owner_id". How would you find the name of a team with an id of 4? Assuming your class only included the code from question 2, how could you find the owner of the same team?

Team.find(4).name

**
owner_of_team_4_id = Team.find(4).owner_id
Owner.find(owner_of_team_4_id)

4. Assume that you added a line to your `Team` class as follows:

```ruby
class Team << ActiveRecord::Base
  belongs_to :owner
end
```

Now how would you find the owner of the team with an id of 4?

**
Team.find(4).owner

5. In a database that's holding students and teachers, what will be the relationship between students and teachers? Draw the schema diagram.

Student Table (belong to teacher)
name
teacher_id

Teacher Table (has many students)
name

6. Define foreign key, primary key, and schema.

Foreign key - a column that exists on a table which has a corresponding primary key on another table.
Primary key - Used to uniquely identify rows or objects in a table.
Schema - the visual representation of a database structure.

7. Describe the relationship between a foreign key on one table and a primary key on another table.
The foreign key on one table is the same as a primary key on another table.

8. What are the parts of an HTTP response?
Http protocol (http/1.1), status code (i.e. 200), english status code equivalent(i.e. ok), headers (e.g. content-length:), and optional body


### Optional Questions

1. Name your five favorite ActiveRecord methods (i.e. methods your models inherit from ActiveRecord) and describe what they do.
This was question #2 above

2. Name your three favorite ActiveRecord rake tasks and describe what they do.
rake db:create - creates empty and unstructured database
rake db:migrate - runs migrations against a database and therefore sets up the db structure and relationships
rake db:seed - fills in the database with data (or rows)
rake db:drop - drops the entire database and its data
rake db:reset - the above 4 rake tasks combined

3. What two columns does `t.timestamps null: false` create in our database?
updated_at and created_at

4. In a database that's holding schools and teachers, what will be the relationship between schools and teachers?
This was question #5 above

5. In the same database, what will you need to do to create this relationship (draw a schema diagram)?
This was question #5 above

6. Give an example of when you might want to store information besides ids on a join table.
???

7. Describe and diagram the relationship between patients and doctors.
A patient belongs to a doctor and a doctor has many patients.

8. Describe and diagram the relationship between museums and original_paintings.
An original painting belongs to a museum and a museum has many original paintings.

9. What could you see in your code that would make you think you might want to create a partial?
Repeated code in several different view templates, such as the same form.
