![Express](https://kinsta.com/wp-content/uploads/2022/04/express-1.png)
- [Website and Documentation](http://expressjs.com/) 
Fast, unopinionated, minimalist web framework for [Node.js](http://nodejs.org/).
```js
const express = require('express')
const app = express()

app.get('/', function (req, res) {
  res.send('Hello World')
})

app.listen(3000)
```

- 001 What is **Express_**
    - use express for reducing repetitive work
- 002 Creating Our First Server with Express **app.listen**
    - [https://expressjs.com/](https://expressjs.com/)
    - `const express = require(”express”)`
    - `var app = express()`
    - `app.listen(3000, function)` see it in `localhost:3000`
- 003 Handling Requests and Responses_ the GET Request **app.get res.send**
    - `app.get(”/”, function(req, res) { } )`
        - it can require (with req) info and respond (with res).
        - eg: `console.log(res)` and `res.send(”hello”)`
- 004 Nodemon Installation **Nodemon**
    - used with `npm install nodemon`
    - restarts server if any changer are applied.
- 005 Understanding and Working with Routes
    - you can create many routes.
- 009 Responding to Requests with HTML Files **res.sendFile(__dirname + “.html”)**
    - to send file `res.sendFile("index.html")`
    - preferred to use `res.sendFile(__dirname + "index.html")`
- 010 Processing Post Requests with Body Parser **body-parser** **req.body action="/" method="post"**
    - use forms in html to connect html with JS
        - `<form action="/" method="post">` in HTML
    - use `body-paerser` in NPM to use these in JS
        - `const bodyParser = require("body-parser");`
        - `app.use(bodyParser.urlencoded({extended: true}));`
    - use **`req.body`** to require the data present in body of the HTML as **Text**