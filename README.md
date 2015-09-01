## Recreating Our Social Media App

![](http://www.bandt.com.au/information/uploads/2014/08/iStock_000027555541_Small-1260x840.jpg)
### Setting Up Sessions

Today's Goal: Use Sessions to allow users to log in and post content!

**Step 1** - Enable Sessions and create a session secret in your application controller. (As always, let Fwitter be your guide) 

**Step 2** - Create a `login.erb` file. The file should render a form with a method of "POST" and an action of "/login". For now, having the user enter their username is enough - we'll deal with passwords in a later module. 

**Step 3** - Setup two routes in your controller - one to get the login form and one to handle the post request. 

**Step 4** - In the post request, take the username the user enters and try to find it in the database. If it's found, you should set the `session[:user_id]` to that user's id. Otherwise, you should redirect to the signup page. 

**Step 5** - Update the way new content is created. After a user logs in, they shouldn't have to identify themselves when creating a new post. The new post should get whatever user_id is stored in the session. 

**Step 6** - Create a route to "/logout" which resets the session data. 

### Bonus Challenges

+ You've got the authentication working, now let's work on authorization. Add some logic to your app so that a user only sees the new content form if they're logged in. 
+ Likewise, add more logic so that logged in users see a link to "/logout", while everyone else sees links to "/login" and "/signup"
+ Refactor your code to use helper methods. It's much nice to see `<% if logged_in? %>` instead of `<% if session[:user_id] %>`. See the Fwitter extra challenges for more help with this!