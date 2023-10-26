# JeffersonCountyLibrary

## Setup
* Fork and Clone this repository
* Run `update-database`

## Exercise (12 points)

Check out a new branch and complete the following tasks **in order**:
* 2 points - There is a bug in our authentication!  Identity looks like it is set up, but we can't register users.  Find and fix this bug! (Hint: this should only take one line of code)
* 2 points - Right now, anyone can 'check out' a book.  Update the application so that only a logged in user can check out a book.
* 4 points - In this application, we have the ability to create new books.  Improve this functionality by:
  * Add a link from the nav-bar to add a book
  * Make sure only Librarians can add a book
* 2 points - Create a descriptive pull request and merge this branch into main
* 2 points - Take a screenshot of a database query result from pgAdmin that clearly shows which users in your database are librarians.  Update this README to include your screenshot below:

  <img width="362" alt="Screenshot 2023-10-26 093348" src="https://github.com/RafiWick/Launch_Mod5Week3Assessment/assets/130600943/7cd245ea-f9cc-4288-882b-4d9abd00ca92">

## Questions (6 points)

Answer the questions below in this README.  Answer these questions as if you are in an interview!

1. What are roles and claims as they relate to Authentication and Authorization?

In Identity A user has both roles and claims. When a user authenicates themselves by logging in the program can now see what roles and claims that this user has. These roles and claims are then checked against to see if the user is authorized to access certain actions. The roles of a user are the categorys of user that that user is. Generaly roles are managed directly in the database so that a user cannot manipulate them. Some examples of roles are admin, superuser, and default (no role). I recently used a role called "Librarian" and the action decorator `[Authorize(Roles = "Librarian")]` on a book create action to ensure that only librarians can add new books. Claims on the other hand are key value pairs that describe the user. Some examples of claims are age and location. claims are frequently changed so they are managed automaticaly in the program. If you consider a sports book that is required by law not to take bets outside of the state they are regestered in. They need to know where the users are located in order to opperate so the claim called location is created with the location services from the users device.

2. How do cookies play a role in authentication and authorization?

Cookies are used to preserve state in an html program. The state that Identity is concerned about is who is logged in. After a user first authenticats themself by logging in Identity creates cookies that can then authenticate the user in each HTTP request until the user logs out, clearing out the cookies. By having an authenticated user the program can then check that user's roles and claims to check if they are authorized for anything that needs specific authorization.

3. If asked to implement Auth in a new .NET application, would you use the Identity framework?

If I were to implement Auth in a new .NET application I would use Identity framework. Identity would be my choice because it is the Auth framework that I am most comfortable with. Identity does a good job abstracting lots of Auth functionality and after a brief setup you only need to add decorators to actions and controllers to require Auth to use them.

## Rubric

This assessment has a total of 18 points.  Earning 12 or higher is a pass!
