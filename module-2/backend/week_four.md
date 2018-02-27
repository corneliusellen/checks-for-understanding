## Week Four Recap

### Instructions
Fork or re-pull this repository. Answer the questions to the best of your ability.

Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week.

Note: When you're done, submit a PR with a reflection in the comments about how this exercise went for you.

### Week 4 Questions

1. What is a cookie?
A piece of data stored on the client's browser

2. What’s the difference between a session and a cookie?
Users cannot edit sessions; they are encrypted. Unlike cookies.
In some applications sessions are stored on the server and cookies are always stored on the client's browser.

3. What’s a flash and when do you want to use flashes?
A flash is a session that self-destructs after opening. It is displayed temporarily on the user's browser.

4. Why do people say “HTTP is stateless”?
Messages sent between them only do one thing and hold one piece of data. Messages don't know about other messages.
*The connection between the browser and the server is lost once the transaction ends.*

5. What’s authentication? Explain.
Authentication is making sure the user says who they day they are. Verifying identity. (e.g. signing into a website.)

6. What’s the difference between authentication and authorization?
Authorization is giving privileges to certain types of users. The privileges can include the ability to view a webpage or interact with the database in some way (CRUD).

7. What’s a before filter?
A callback in the controller.
Something that runs before any action in that controller.
**Callbacks allow you to trigger logic before or after an alteration of an object’s state.**

8. How do we keep track of a user once they’ve logged in?
Through the session (1 session, but many keys).

9. When do you want to namespace a resource? When do you want to nest a resource? What's the differences between those two approaches?
You should namespace a resource when there is no corresponding model. It organizes code more effectively (usually admin is namespaced in order to keep track of all the admin views and controllers).
*Nest when there are dependent resources i.e. you need a company for a job.*

10. At a high level, what tools can you use to implement authorization? How would you use them?
Namespacing and using filters.

11. What's an enum, and what advantages does it offer? What data type needs to be in your database to use an enum? Where do you declare an enum?
Enums are attributes that only have a few options and numbers represent the actual values.
*they have the flexibility of a string, but the speed and efficiency of an integer.*
Implement by:
On model:
enum status: [:in_stock, :out_of_stock, :ordered]

In migration:
add_column :books, :status, :integer, default: 0

12. What are some strategies you can use to keep your views DRY?
Partials
POROs


### Reviews Questions
13. Given the following array of hashes, how would I print an alphabetical list of holidays?
```ruby
[
 {holiday: {name: "St Patrick's Day", supplies: ["Corned Beef and Cabbage"]},
 {holiday: {name: "Halloween", supplies: ["Candy", "Costume"]},
 {holiday: {name: "Hanukkah", supplies: ["Menorah"]}
]
```  
14. How would you clean incoming data to ensure "$300" or "300.00" is stored as 300?


### Self Assessment:
Choose One:
* I was able to answer every question without relying on outside resources
* I was able to answer most questions independently, but utilized outside resources for a few
* I was able to answer a few questions independently, but relied heavily on outside resources

Choose One:
* I feel confident about the content presented this week
* I feel comfortable with the content presented this week
* I feel overwhelmed by the content presented this week
* I feel quite lost by the content presented this week
