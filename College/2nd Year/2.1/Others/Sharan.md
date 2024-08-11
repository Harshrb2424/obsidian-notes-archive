
#### validation.js

```js
const form = document.getElementById('form');
const fullName = document.getElementById('uname');
const email = document.getElementById('email');
const phoneNumber = document.querySelector('input[type="tel"]');
const password = document.getElementById('password');
const confirmPassword = document.getElementById('cpassword');
const termsCheckbox = document.getElementById('tc');

form.addEventListener('submit', function (e) {
    e.preventDefault();

    let errors = [];

    // Validation for Full Name
    if (fullName.value.length < 5) {
        errors.push('Full Name must be at least 5 characters.');
    }

    // Validation for Phone Number
    const phoneNumberRegex = /^[0-9]{10}$/;
    if (!phoneNumberRegex.test(phoneNumber.value) || phoneNumber.value === '123456789') {
        errors.push('Phone Number should be a 10-digit number and should not be 123456789.');
    }

    // Validation for Password
    if (
        password.value.length < 8 ||
        password.value.toLowerCase() === 'password' ||
        password.value.toLowerCase() === fullName.value.toLowerCase()
    ) {
        errors.push('Password must be at least 8 characters and cannot be "password" or your Full Name.');
    }

    // Validation for Password match
    if (password.value !== confirmPassword.value) {
        errors.push('Passwords do not match.');
    }

    // Validation for Terms and Conditions checkbox
    if (!termsCheckbox.checked) {
        errors.push('Please agree to the terms and conditions.');
    }

    // This display errors if any condition not met
    if (errors.length > 0) {
        alert(errors.join('\n'));
    } else {
        form.reset();
        window.location.href = 'submitted.html';
    }
});

```

#### form.html

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Form Validation</title>
    <link rel="stylesheet" href="style.css">  
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@300;400&display=swap" rel="stylesheet">
</head>
<body>
    <div class="container">
        <div class="header">
            <h2>Register Here</h2>
        </div>
        <form action="submitted.html" method="post" class="form" id="form">
            <div class="field">
                <label >Full Name</label>
                <input type="text" placeholder="xyz" id="uname" required>
            </div>
            <div class="field ">
                <label>Email ID</label>
                <input type="email" placeholder="abc@gmail.com" id="email" required>
            </div>
            <div class="field">
                <label>Phone Number</label>
                <input type="tel" placeholder="xxxxxxxxx" required>                
            </div>
            <div class="field">
                <label>Password</label>
                <input type="password" placeholder="password" id="password" required>                
            </div>
            <div class="field">
                <label>Confirm Password</label>
                <input type="password" placeholder="password" id="cpassword" required>                
            </div>
            <div class="field">
                <input type="checkbox" id="tc" class="terms" required>
                <label>I agree to terms and conditions</label>                               
            </div>
            <input style="cursor: pointer;" type="submit" id = "submit" class="button">
        </form>
    </div>
    <script src = "validation.js"></script>
</body>
</html>

```

#### style.css

```css
*{
    box-sizing: border-box;
    margin: 0;
    padding: 0;
    outline: none;
    font-family: 'Montserrat', sans-serif;
}

body{
    display: flex;
    justify-content: center;
    align-items: center;
    background-color: #607680;
    min-height: 100vh;
    margin: 0;
}

.container{
    background-color: white;
    border-radius: 5px;
    width: 400px;
    max-width: 100%;
    overflow: hidden;
}
.header{
    background-color: #f7f7f7;
    padding: 20px 40px;
    border-bottom: 1px solid #f0f0f0;
}

.header h2{
    margin: 0;
}

.form{
    padding: 30px 40px;
}

.field{
    margin-bottom: 10px;
    padding-bottom: 20px;
    position: relative;
}
.field label{
    display: inline-block;
    margin-bottom: 5px;
}

.field input:not(.terms){
    display: block;
    border-radius: 4px;
    border:2px solid #f0f0f0;
    font-size: 14px;
    width: 100%;
    padding: 10px;
}
.form .button{
    background-color: rgb(90, 104, 235);
    border: 2px solid rgb(90, 104, 235);
    color: white;
    padding: 10px;
    display: block;
    width: 100%;
    font-size: 16px;
}
```