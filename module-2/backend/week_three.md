## Week Three Recap

### Instructions
Fork this repository. Be sure to pull the latest changes to your local repo. Answer the questions to the best of your ability.

Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week.

Note: When you're done, submit a PR with a reflection in the comments about how this exercise went for you.

### Week 3 Questions

1. What is the entry at the command line to create a new rails app?
*rails new <project_name> -T -d="postgresql" --skip-spring --skip-turbolinks

2. What do Models generally inherit from in rails?
*ApplicationRecord

3. What do Controllers generally inherit from in a rails project?
*ApplicationController

4. How would I create a route if I wanted to see a specific horse in my routes file assuming I'm sticking to standard conventions and that I didn't want other CRUD functionality?
*resources :horses, only: [:show]

5. What rake task is useful when looking at routes, and what information does it give you?
*rails routes - gives you the prefix(or path helper), http verb, URI route, and controller+action

6. What is an example of a route helper? When would you use them?
*vehicles_path or vehicle_path(<vehicle object>) - use them to DRY up your code when referring to links and so you're not typing out long URIs.
  
7. What's the difference between what `_url` and `_path` return when combined with a routes prefix?
*_url returs the full URL and _path returns only the URI

8. What are strong params and why are they necessary?
*strong params is a method you MUST add in each of your controllers to check the proper params are coming through. Rails will not let your blindly pass params to your CRUD methods. This is necessary for security - for example a mischievous person could go into Postman, send a post request to your application for parameters that are not correct and mess up your program somehow... but with strong params that mischievous person will get an error back along the lines of: Invalid Authenticity Token.

9. What role does `form_for` play in helping us create our forms?
*It helps us more easily create forms without using html's tedious form elements. It 

10. How does `form_for` know where to submit the user's input?
*I'm not sure on this one, but I think it is because of the corresponding name of the html.erb file. If the file is named "new.html.erb" the form will submit the input as a "Create" action to the controller where it came from. If the file was named "edit.html.erb" the form will submitt the input as an "Update" action.

11. Create a form using a `form_for` helper to create a new `Horse`. 
*<%= form_for @horse do |f| %>
*<%= f.label :name %>
*<%= f.text_field :name %>

*<%= f.submit %>
*<% end %>

12. Why do we want to validate our models?
*We want to make sure a user cannot create an instance of a resource without inputting all of it's required attributes. Another validation is for uniquness so we may not want two of the exact same instances or a resource.

13. What are the steps of the DNS lookup?
*The browser queries the computer's cache first. If it's not there, the browser has probably never visited the site before so the operating system (specifically the resolving name server) queries a series of other servers including the root name, TLD (top level domain, which is like .com, .org, .gov...) and authoritative servers (in that order) to find the IP address. Once it has the numeric IP address, it returns in back to the browser.


### Review Questions
14. How would you call the method `prance` from within the method `move` on a `Horse` instance?
*def move
  prance
end 

15. Given the following hash:

```ruby
furniture = {table: {height: 3, color: "red"}, purchased: true}
```
What is the different between how you would return true vs returning 3?
furniture[:table][:height]
furniture[:purchased]

16. What is inheritance?
Classes taking on (inheriting) other parent classes's methods.

### Self Assessment:
Choose One:
I was able to answer every question without relying on outside resources
* I was able to answer most questions independently, but utilized outside resources for a few
I was able to answer a few questions independently, but relied heavily on outside resources 

Choose One:
* I feel confident about the content presented this week
I feel comfortable with the content presented this week
I feel overwhelmed by the content presented this week
I feel quite lost by the content presented this week
