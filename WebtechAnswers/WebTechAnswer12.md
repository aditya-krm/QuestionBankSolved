# Question:

12. Different types of CSS (inline, embedded, external) with examples.

# Answer:

## Different Types of CSS with Examples:

There are three main ways to implement CSS styles on your web page:

**1. Inline Styles:**

*   This method applies styles directly to an individual HTML element using the `style` attribute within the opening tag.
*   **Example:**

```html
<h1 style="color: blue; font-size: 20px;">This is a blue heading</h1>
```

*   **Advantages:**
    *   Quick and easy for simple styling.
    *   Useful for one-off styles that don't need to be repeated.
*   **Disadvantages:**
    *   Makes HTML code cluttered and less readable.
    *   Difficult to maintain and update styles consistently.
    *   Not recommended for larger projects.

**2. Embedded Styles (Internal Stylesheet):**

*   This method uses the `<style>` tag within the `<head>` section of your HTML document to define styles for the entire page.
*   **Example:**

```html
<!DOCTYPE html>
<html>
<head>
  <style>
    h1 {
      color: blue;
      font-size: 20px;
    }
    p {
      font-family: Arial, sans-serif;
    }
  </style>
</head>
<body>
  <h1>This is a blue heading</h1>
  <p>This is a paragraph with Arial font.</p>
</body>
</html>
```

*   **Advantages:**
    *   Keeps styles separate from HTML content, improving organization.
    *   Easier to manage styles for a single page.
*   **Disadvantages:**
    *   Styles are not reusable across multiple pages.
    *   Can still lead to code duplication if similar styles are used on different pages.

**3. External Stylesheet:**

*   This method uses a separate CSS file (with a .css extension) to store all the styles. The CSS file is then linked to the HTML document using the `<link>` tag in the `<head>` section.
*   **Example:**

**style.css:**

```css
h1 {
  color: blue;
  font-size: 20px;
}

p {
  font-family: Arial, sans-serif;
}
```

**index.html:**

```html
<!DOCTYPE html>
<html>
<head>
  <link rel="stylesheet" href="style.css">
</head>
<body>
  <h1>This is a blue heading</h1>
  <p>This is a paragraph with Arial font.</p>
</body>
</html>
```

*   **Advantages:**
    *   Centralized location for styles, making maintenance and updates efficient.
    *   Promotes consistency across multiple pages.
    *   Improves page load speed as the CSS file is cached by the browser.
*   **Disadvantages:**
    *   Requires an additional file to manage.
    *   Might require more planning and organization for larger projects.

**In general, using external stylesheets is considered the best practice for most projects due to its maintainability, reusability, and performance benefits.** 
