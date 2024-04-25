# Question:

9. Design the following: A html page “login.html” contains two text input fields, on submit it is redirected to a page “account.html”

# Answer:

## Building a Login Page with HTML and Redirection

Here's how to design the `login.html` page and achieve redirection to `account.html` upon submission:

**login.html:**

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Login Page</title>
</head>
<body>
    <h1>Login</h1>
    <form action="account.html" method="post">
        <label for="username">Username:</label><br>
        <input type="text" id="username" name="username" required><br><br>

        <label for="password">Password:</label><br>
        <input type="password" id="password" name="password" required><br><br>

        <input type="submit" value="Login">
    </form>
</body>
</html>
```

**Explanation:**

1. **Basic HTML Structure:** The code starts with the basic HTML structure including `DOCTYPE`, `html`, `head`, and `body` tags.
2. **Form Creation:** A `<form>` element is created with the following attributes:
    * **action="account.html"**: This specifies that upon submitting the form, the browser should redirect to the "account.html" page.
    * **method="post"**: This indicates that the form data will be sent to the server using the HTTP POST method.
3. **Input Fields:** Two input fields are created:
    * **Username:** A text input field with the id "username" and name "username" for users to enter their usernames. The `required` attribute ensures the field must be filled.
    * **Password:** A password input field with the id "password" and name "password" for users to enter their passwords. The `required` attribute is also present.
4. **Submit Button:** An `<input type="submit">` creates a button that, when clicked, submits the form data and triggers the redirection to "account.html".

**Important Considerations:**

* This example provides a basic structure for a login page. In a real application, you would need to implement server-side validation and processing of the login credentials. 
* You might also want to include additional features like "remember me" functionality or password reset options.
* Styling the page with CSS can improve its appearance and user experience.

**Next Steps:**

* Create the "account.html" page with content relevant to logged-in users.
* Implement server-side logic to handle user authentication and authorization.
* Consider adding security measures like password hashing and secure connections (HTTPS). 
