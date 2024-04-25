# Question:

11. Design a web page using HTML / CSS of a course registration page that contains course-related information, and user information. On submit that page must be redirected to “welcome.html” page.

# Answer:

## Course Registration Page Design with HTML & CSS

Due to the limitations of this text-based environment, I cannot directly create and display a functional web page. However, I can provide you with the HTML and CSS code structure and explain the elements involved. You can then copy and paste this code into separate HTML and CSS files and open the HTML file in a web browser to see the registration page.

**HTML (index.html):**

```html
<!DOCTYPE html>
<html>
<head>
  <title>Course Registration</title>
  <link rel="stylesheet" type="text/css" href="style.css">
</head>
<body>
  <h1>Course Registration</h1>
  <form action="welcome.html" method="post">
    <h2>Course Information</h2>
    <label for="course">Select Course:</label>
    <select id="course" name="course">
      <option value="webdev">Web Development</option>
      <option value="datascience">Data Science</option>
      <option value="machinelearning">Machine Learning</option>
    </select>
    
    <h2>User Information</h2>
    <label for="name">Full Name:</label>
    <input type="text" id="name" name="name" required>
    
    <label for="email">Email:</label>
    <input type="email" id="email" name="email" required>
    
    <input type="submit" value="Register">
  </form>
</body>
</html>
```

**CSS (style.css):**

```css
body {
  font-family: sans-serif;
}

h1, h2 {
  text-align: center;
}

form {
  max-width: 400px;
  margin: 20px auto;
  padding: 20px;
  border: 1px solid #ccc;
  border-radius: 5px;
}

label {
  display: block;
  margin-bottom: 5px;
}

input[type="text"],
input[type="email"],
select {
  width: 100%;
  padding: 10px;
  margin-bottom: 15px;
  border: 1px solid #ccc;
  border-radius: 3px;
}

input[type="submit"] {
  background-color: #4CAF50;
  color: white;
  padding: 12px 20px;
  border: none;
  border-radius: 3px;
  cursor: pointer;
}
```

**Explanation:**

*   **HTML:**
    *   The form uses the `post` method to submit data to "welcome.html".
    *   Dropdown for course selection, text fields for name and email are included.
    *   The submit button triggers the redirection.
*   **CSS:**
    *   Basic styling for the page elements like font, alignment, form container, input fields, and button.

**Remember:**

*   You'll need to create a separate "welcome.html" file for the redirection to work.
*   This is a basic structure. You can enhance it with more styling, validation, and functionality as needed. 

**Additional Features (not implemented here):**

*   **Input validation:** Ensure users enter valid data (e.g., email format).
*   **More course details:** Add descriptions or prerequisites for each course.
*   **Server-side processing:** Use a server-side language (like PHP, Python) to handle form data and store registrations in a database. 
