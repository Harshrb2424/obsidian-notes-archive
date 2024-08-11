![Node js](https://upload.wikimedia.org/wikipedia/commons/thumb/d/d9/Node.js_logo.svg/1200px-Node.js_logo.svg.png)

Node.js® is an open-source, cross-platform JavaScript runtime environment.

```js
import express from "express";
import bodyParser from "body-parser";
import pg from "pg";

const app = express();
const port = 3000;
app.use(bodyParser.urlencoded({ extended: true }));
app.use(express.static("public"));

const client = new pg.Client({
  user: "postgres",
  host: "localhost",
  database: "NodeProjects",
  password: "2424",
  port: 2424,
});
await client.connect();
app.get("/", async (req, res) => {
  res.render("test.ejs");
  const result = await client.query("SELECT * FROM public.todo");
  const items = result.rows;
  res.render("index.ejs", {
    listTitle: "Today",
    listItems: items,
  });
});
app.listen(port, () => {
  console.log(`Server running on port ${port}`);
});
```

- 004 The Power of the Command Line and How to Use Node **node**
    - `node index.js` to execute JS in it
- 005 The Node REPL (Read Evaluation Print Loops) **node .exit**
    - `node` to use Node REPL (Read Evaluation Print Loops) same as chrome console.
    - `.exit` or ctrl+C, ctrl+C to exit Node REPL
- 006 How to Use the Native Node Modules **require**
    - you can use modules present in node with `const fs = require(”fs”)`
    - [https://nodejs.org/docs/latest/api/](https://nodejs.org/docs/latest/api/)
- 007 The NPM Package Manager and Installing External Node Modules **npm init**
    - you can use external modules with [NPM](https://www.npmjs.com/)
    - start with `npm init`

The Concept of **Scope** in the Context of Javascript
    - Scope
        - in function
            - `var` , `let` , `const` are Local Variables
        - in JS
            - `var` , `let` , `const` are Global Variables
        - in if/else
            - `var` is Global Variable, `let` , `const` but are Local Variables

- 024 Javascript ES6 Map_Filter_Reduce
	
	_//Map -Create a new array by doing something with each item in an array._
	
	- `let variable = array.map(function createItem(item) { return clg(item.name) })`
	
	_//Filter - Create a new array by keeping the items that return true._
	
	- `let variable = array.filter(function createItem(item) { return item.price < 10 })`
	
	_//Reduce - Accumulate a value by doing something to each item in an array._
	- To find total price, sum, p.
	- `array.reduce(function createItem(accumulater, item) { return accumulater + item.price })`
	
	_//Find - find the first item that matches from an array._
	- ES6
	- `array.find**(function createItem(item) { return item.price > 1000 })**`
		- gets item
	
	_//FindIndex - find the index of the first item that matches._
	- ES6
	- `array.find**(function createItem(item) { return item.price > 1000 })**`
		- gets item index
- 025 Javascript ES6 Arrow functions
	
	- `function (props) {return props.name}` is same as
	- `(props) => props.name`