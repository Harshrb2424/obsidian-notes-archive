# **1. Build a responsive web application for shopping cart with registration, login, catalog and cart pages using CSS3 features, flex and grid**
## AIM: 
Build a responsive web application for shopping cart with registration, login, catalog and cart pages using CSS3 features, flex and grid.
## DESCRIPTION: 
HTML, CSS, and JavaScript are essential components for creating a functional responsive web application. A condensed example of a shopping cart with registration, login, 
catalogue, and cart pages is provided.
## Project Structure:
1. index.html - Main HTML file containing the structure of the web application.
2. styles.css - CSS file for styling the web pages
### index.html

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <link rel="stylesheet" href="styles.css">
    <title>Shopping Cart</title>
</head>

<body>
    <header>
        <h1>Shopping Cart</h1>
        <nav>
            <ul>
                <li><a href="#home">Home</a></li>
                <li><a href="#catalog">Catalog</a></li>
                <li><a href="#cart">Cart</a></li>
                <li><a href="#login">Login</a></li>
                <li><a href="#register">Register</a></li>
            </ul>
        </nav>
    </header>

    <main>
        <section id="home">
            <h2>Welcome to our Shopping Cart!</h2>
        </section>
        <section id="catalog">
            <h2>Catalog</h2>
            <div class="product">
                <img src="product1.jpg" alt="Product 1">
                <h3>Product 1</h3>
                <p>Description of Product 1. Price: ₹199</p>
                <button>Add to Cart</button>
            </div>
        </section>
        <section id="cart">
            <h2>Shopping Cart</h2>
            <ul>
                <li>
                    <img src="product1.jpg" alt="Product 1">
                    <span>Product 1</span>
                    <span>₹199</span>
                    <button>Remove</button>
                </li>
            </ul>
            <p>Total: ₹199</p>
            <button>Checkout</button>
        </section>
        <section id="login">
            <h2>Login</h2>
            <form>
                <label for="username">Username:</label>
                <input type="text" id="username" name="username" required>

                <label for="password">Password:</label>
                <input type="password" id="password" name="password" required>

                <button type="submit">Login</button>
            </form>
        </section>
        <section id="register">
            <h2>Registration</h2>
            <form>
                <label for="username">Username:</label>
                <input type="text" id="username" name="username" required>

                <label for="email">Email:</label>
                <input type="email" id="email" name="email" required>

                <label for="password">Password:</label>
                <input type="password" id="password" name="password" required>

                <button type="submit">Register</button>
            </form>
        </section>
    </main>

    <footer>
        <p>&copy; 2023 Shopping Cart</p>
    </footer>
</body>
</html>
```
### styles.css

```css
body {
    font-family: "Arial", sans-serif;
    margin: 0;
    padding: 0;
}
header {
    background-color: #333;
    color: #fff;
    padding: 1em;
    text-align: center;
}
nav {
    display: flex;
    justify-content: center;
    margin-top: 1em;
}
nav ul {
    list-style: none;
    display: flex;
}
nav ul li {
    margin: 0 10px;
}
nav a {
    text-decoration: none;
    color: #fff;
}
main {
    padding: 20px;
}
.product {
    border: 1px solid #ccc;
    padding: 10px;
    margin-bottom: 10px;
}
form {
    max-width: 400px;
    margin: 0 auto;
}
form label {
    display: block;
    margin-bottom: 5px;
}
form input {
    width: 100%;
    padding: 8px;
    margin-bottom: 10px;
}
form button {
    background-color: #333;
    color: #fff;
    padding: 10px;
    border: none;
    cursor: pointer;
}
footer {
    background-color: #333;
    color: #fff;
    text-align: center;
    padding: 1em;
}
```

## Explanation 
1. HTML Structure: The HTML file consists of a header, navigation, and a main content area, initially empty but dynamically populated using JavaScript.
2. CSS Styles: The CSS file offers basic styling for header, navigation, and main content area, which can be customized according to your design needs.
## Output: 
The shopping cart application's basic structure is displayed in index.html, with the 
catalog section containing dummy product data

![[Pasted image 20231210192518.png]]
# **2. Make the above web application responsive using Bootstrap framework**
## AIM: 
Make the above web application responsive web application using Bootstrap framework
## DESCRIPTION: 
Bootstrap is a popular CSS framework that makes it easy to create responsive web applications.
The previous example can be modified using Bootstrap by following these steps:
## Project Structure: 
1. index.html - Main HTML file containing the structure of the web application 
with Bootstrap.
### index.html

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/css/bootstrap.min.css" rel="stylesheet" />
    <title>Shopping Cart</title>
</head>

<body>
    <header class="bg-dark text-white text-center py-3">
        <h1>Shopping Cart</h1>
        <nav class="mb-3">
            <ul class="nav justify-content-center">
                <li class="nav-item">
                    <a class="nav-link" href="#home">Home</a>
                </li>
                <li class="nav-item">
                    <a class="nav-link" href="#catalog">Catalog</a>
                </li>
                <li class="nav-item">
                    <a class="nav-link" href="#cart">Cart</a>
                </li>
                <li class="nav-item">
                    <a class="nav-link" href="#login">Login</a>
                </li>
                <li class="nav-item">
                    <a class="nav-link" href="#register">Register</a>
                </li>
            </ul>
        </nav>
    </header>

    <main class="container mt-4">
        <section id="home">
            <h2>Welcome to our Shopping Cart!</h2>
        </section>

        <section id="catalog">
            <h2>Catalog</h2>
            <div class="row">
                <div class="col-md-4 mb-4">
                    <div class="card">
                        <img src="product1.jpg" alt="Product 1" class="card-img-top" />
                        <div class="card-body">
                            <h5 class="card-title">Product 1</h5>
                            <p class="card-text">Description. Price: ₹199</p>
                            <button class="btn btn-primary">Add to Cart</button>
                        </div>
                    </div>
                </div>

                <div class="col-md-4 mb-4">
                    <div class="card">
                        <img src="product2.jpg" alt="Product 2" class="card-img-top" />
                        <div class="card-body">
                            <h5 class="card-title">Product 2</h5>
                            <p class="card-text">Description. Price: ₹249</p>
                            <button class="btn btn-primary">Add to Cart</button>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <section id="cart">
            <h2>Shopping Cart</h2>
            <ul class="list-group">
                <li class="list-group-item d-flex justify-content-between align-items-center">
                    <img src="product1.jpg" alt="Product 1" style="max-width: 50px; height: auto" />
                    <span>Product 1</span>
                    <span>₹199</span>
                    <button class="btn btn-danger">Remove</button>
                </li>

                <li class="list-group-item d-flex justify-content-between align-items-center">
                    <img src="product2.jpg" alt="Product 2" style="max-width: 50px; height: auto" />
                    <span>Product 2</span>
                    <span>₹249</span>
                    <button class="btn btn-danger">Remove</button>
                </li>
            </ul>
            <p class="mt-3">Total: ₹498</p>
            <button class="btn btn-primary">Checkout</button>
        </section>

        <section id="login">
            <h2>Login</h2>
            <form>
                <label for="username" class="form-label">Username:</label>
                <input type="text" id="username" class="form-control" required />

                <label for="password" class="form-label">Password:</label>
                <input type="password" id="password" class="form-control" required />

                <button type="submit" class="btn btn-primary mt-3">Login</button>
            </form>
        </section>

        <section id="register">
            <h2>Registration</h2>
            <form>
                <label for="username" class="form-label">Username:</label>
                <input type="text" id="username" class="form-control" required />

                <label for="email" class="form-label">Email:</label>
                <input type="email" id="email" class="form-control" required />

                <label for="password" class="form-label">Password:</label>
                <input type="password" id="password" class="form-control" required />

                <button type="submit" class="btn btn-primary mt-3">Register</button>
            </form>
        </section>
    </main>

    <footer class="bg-dark text-white text-center py-3">
        <p>&copy; 2023 Shopping Cart</p>
    </footer>
</body>

</html>
```
## Explanation:

1. **Bootstrap Integration:** In the `<head>` section, we added links to the Bootstrap CSS and JS files from a CDN (Content Delivery Network). This allows us to use Bootstrap's styling and functionality.

2. **Bootstrap Classes:** We applied Bootstrap classes to the HTML elements. For example, we used `container` to create a responsive fixed-width container and various utility classes for styling the header and navigation.

3. **Responsive Navigation:** Bootstrap's grid system and utility classes help in creating a responsive navigation bar. The `justify-content-center` class is used to center the navigation links.

4. **Responsive Main Content:** The `container` class ensures that the main content area is responsive. Bootstrap will automatically adjust the width based on the screen size.

## Output:
When you open `index.html` in a web browser, you'll see that the web application is now responsive. The Bootstrap framework takes care of making the layout adapt to different screen sizes, providing a more user-friendly experience on various devices.

Remember to test the responsiveness by resizing your browser or using different devices to see how the layout adjusts.

![[Pasted image 20231210193543.png]]

# **3. Use JavaScript for doing client–side validation of the pages implemented in experiment 1 and experiment 2**

## AIM

Use JavaScript for doing client-side validation of the pages implemented in:
1. Experiment 1: Build a responsive web application for a shopping cart with registration, login, catalog, and cart pages using CSS3 features, flex, and grid.
2. Experiment 2: Make the above web application a responsive web application using the Bootstrap framework.

## DESCRIPTION

To perform client-side validation using JavaScript, you can add scripts to validate user inputs on the registration and login pages. The modifications for both experiments are listed below:

1. **Experiment 1 Modifications:**
   - Implement JavaScript scripts to validate user inputs on the registration and login pages.
   - Ensure that user inputs meet the required criteria (e.g., valid email format, password strength).

2. **Experiment 2 Modifications:**
   - Integrate JavaScript scripts for client-side validation as described in Experiment 1.
   - Leverage Bootstrap's form validation classes and features for a seamless validation experience.
   - Ensure that the responsive web application maintains validation functionality across different device sizes.

	Make sure to include this `index.js` file in your HTML document after including the Bootstrap JavaScript file.

```html
<script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/js/bootstrap.bundle.min.js"></script>
<script src="index.js"></script>

```

### Experiment 1: Responsive Web Application without Bootstrap

```javascript
function validateCart() {
  var cartItems = document.querySelectorAll('.cart-item');
  
  if (cartItems.length === 0) {
    alert('Your cart is empty. Please add items before proceeding.');
    return false;
  }
  return true;
}

function validateLogin() {
  var username = document.getElementById('login-username').value;
  var password = document.getElementById('login-password').value;

  if (!username || !password) {
    alert('Please enter both username and password.');
    return false;
  }
  return true;
}
function validateRegistration() {
  var username = document.getElementById('register-username').value;
  var email = document.getElementById('register-email').value;
  var password = document.getElementById('register-password').value;

  if (!username || !email || !password) {
    alert('Please fill out all fields.');
    return false;
  }
  return true;
}
```

### Experiment 2: Responsive Web Application with Bootstrap

```javascript
function validateCart() {
  var cartItems = document.querySelectorAll('.cart-item');
  
  if (cartItems.length === 0) {
    alert('Your cart is empty. Please add items before proceeding.');
    return false;
  }
  return true;
}

function validateLogin() {
  var username = document.getElementById('login-username').value;
  var password = document.getElementById('login-password').value;

  if (!username || !password) {
    alert('Please enter both username and password.');
    return false;
  }
  return true;
}
function validateRegistration() {
  var username = document.getElementById('register-username').value;
  var email = document.getElementById('register-email').value;
  var password = document.getElementById('register-password').value;

  if (!username || !email || !password) {
    alert('Please fill out all fields.');
    return false;
  }
  return true;
}
```

## Explanation

1. **Validation Functions:**
   - Added two validation functions, `validateRegistration` and `validateLogin`.
   - These functions retrieve form inputs and perform basic validation.
   - You can enhance the validation logic based on specific requirements.

2. **Form Modification:**
   - Added the `onsubmit` attribute to the registration and login forms.
   - The attribute calls the respective validation functions when the forms are submitted.
   - For Bootstrap forms, added the `novalidate` attribute to prevent default browser validation.
   - Handling validation using JavaScript provides a better user experience.

## Outputs

### Experiment 1:

![[Pasted image 20231210194904.png]]
### Experiment 2:

![[Pasted image 20231210195100.png]]

# **4. Explore the features of ES6 like arrow functions, callbacks, promises, async/await. Implement an application for [[reading the weather information]] from openweathermap.org and display the information in the form of a graph on the web page**

# **5. Develop a Java stand-alone application that connects with the database (Oracle / MySQL) and perform the CRUD operation on the database tables**

# **6. Create an XML for the bookstore. Validate the same using both DTD and XSD**