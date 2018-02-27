### Week 5 Questions

Re-pull from this respository. Answer the questions to the best of your ability. Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week (which is a TON!).

Note: When you're done, submit a PR.

### Week 5 Questions
1. How do we make flash messages display on a page?
Allow the flash to render by putting the follow in the application view:
<% if flash[:notice] %> <%= flash[:notice] %> <% end %>

2. Where is cart information/temporary information usually stored?
In a session.

3. What might be some reasons not to store a cart in our database? Are there any reasons why we would want to persist that information?
It might take up too much storage on our database, because every time a visitor or user puts something is their cart it would require our system to save the cart in our db. We may want to persist that information if we want user's shopping patterns to sell to advertisers ???

4. What is the purpose of the asset pipeline?
The purpose is to speed up the process of serving our static assets.

5. Why do we precompile our assets?
Precompiling makes each of your assets receive a fingerprint, which will indicate any updates that you may deploy down the line and tells user's browsers to fetch the updated asset.
*When in production we want our assests complied, minified, fingerprinted, and cached. Heroku does this for you automatically when you build. However, you might need to debug production in which case you want to precomplie your assets so you can see the version that would be used in production. Important to remember to clobber those assets though before you try to re-build on Heroku as Heroku won't precompile if you already have compiled assets in your public folder.*

6. What do each of the following tags do?

```ruby
<%= stylesheet_link_tag "application" %>
<%= javascript_include_tag "application" %>
<%= image_tag "rails.png" %>
```

Links to your stylesheet manifest
Links to your javascript manifest
Links to a specific image

7. What are some of the elements of a great read me? What are some of the benefits of taking the time to update a readme for our project?
Informative header and description
How to install your application
How to test you application
How to contribute to your application

A great readme will make your application more attractive to other developers and employers.

8. What are the top four accessibility issues that we as developers should be aware of?
Visible, Mobility and Cognition

9. `before_save` is an example of a what? Where in our Rails application would we find a `before_save`?
This is an example of a callback. A filter is something to execute before some of all of the controller actions. It would be found in the MODEL.

10. Given the following object, how would we create a scope for all users who are active?

```ruby
User.create(name: "Happy", active: true)
```
scope :active, -> { where(active: true)}

11. What is the difference between a scope and a class method?
A class methods works on ALL instances of the class. A scope is something you can use when you are constantly making the same query, so you can use a scope to always return the same value.
**Scopes should be used to return a subset of records/objects of that class. A class method can be used to find a much broader variety of information.**

### Review Questions:  
12. Given the following hash:  

```ruby
{cart: {"17" => 4, "204" => 52, "29" => 22}}
```

  12a. How would you add item with id of 48 with a quantity of 4?
  You would need to assign the cart to a variable, like cart. Then:
  cart[:cart]["48"] = 4

  12b. How would you increase the quantity of item 29?  
  cart[:cart]["29"].to_i += quantity (the to_i makes the nil a 0)

  12c. How would you find out how many items your user is thinking about purchasing?   
  cart[:cart].values.sum

13. What is polymorphism? How does it relate to duck-typing? What are two ways you use this in everyday Rails applications?  
"It is the programming language's ability to process objects differently depending on their data type or class"

**Polymorphism is the practice of creating methods of the same name on different types of objects. Duck-typing is the idea of if it looks like a duck and acts like a duck, treat it like a duck. a.k.a. if it acts like a data type you're used to treat it like that data type. You've benefited from this when interacting with ActiveRecord::Associations, ActiveRecord:Relations (just like Arrays) or Sessions (just like Hashes).**

14. How would you clean the string "(630) 854-5483" to "630.854.5483"?  
Assign the string to a variable like so number = "(630) 854-5483"
Then:
 num.tr!("()\- ", "") num.insert(3, ".") num.insert(7, ".")

### Self Assessment:
Choose One:
I was able to answer every question without relying on outside resources
I was able to answer most questions independently, but utilized outside resources for a few
* I was able to answer a few questions independently, but relied heavily on outside resources

Choose One:
* I feel confident about the content presented this week
I feel comfortable with the content presented this week
I feel overwhelmed by the content presented this week
I feel quite lost by the content presented this week
