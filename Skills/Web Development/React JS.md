 - 33 - React.js
    - 001 What is React_
        
        - React is a frontend framework and is popular
    - 004 Introduction to JSX and Babel
        
        - in ./public/index.html **to connect to index.js and modify .root**
        
        ```html
        <body>
            <div id="root"></div>
            <script src="../src/index.js" type="text/javascript"></script>
          </body>
        ```
        
        - in ./src/index.js
        
        ```jsx
        import React from "react";
        import ReactDOM from "react-dom";
        
        ReactDOM.render(<h1>Hello World!</h1>,document.getElementById("root"));
        ```
        
        - `ReactDOM.render(what to change, where to change);`
        - makes it easy
    - 005 JSX Code Practice
        
        - you can only have one html element in it.
            - to use more use `div` and everything else in that `div`
        
        ```jsx
        ReactDOM.render(
          <div>
            <h1>Top Games</h1>
            <ul>
              <li>Valorent</li>
              <li>Grand Theft Auto V</li>
              <li>Fall Guys: Ultimate Knockout</li>
            </ul>
          </div>,
          document.getElementById("root")
        );
        ```
        
    - 006 Javascript Expressions in JSX & ES6 Template Literals
        
        - in HTML you can have JS with `{name}` these brackets any JS code which gives 1 result **(expression)**.
        - Only expressions can be added not statements.
            - `{fname} {lname}`
            - `{fname + ” ” + lname}`
            - `{`${fname} ${lname}`}` → ES6 useing string ````
    - 007 Javascript Expressions in JSX Practice
        
        - get year with `(new Data().getFullYear())`
    - 008 JSX Attributes & Styling React Elements
        
        - add classes with `className=”heading”` because it is with JSX
        - [https://www.w3schools.com/tags/ref_standardattributes.asp](https://www.w3schools.com/tags/ref_standardattributes.asp)
    - 009 Inline Styling for React Elements
        
        - add CSS with JS `style={{color: red}}`
    - 011 React Components
        
        - separate repetitive elements
        
        ```jsx
        import React from "react";
        
        function Heading() {
          return (
            <h1 className="heading" style={customStyle}>
              {greeting}
            </h1>
          );
        }
        
        export default Heading;
        ```
        
    - 012 React Components Practice
        
        - common practice
            - in index.js
        
        ```jsx
        import React from "react";
        import ReactDOM from "react-dom";
        import App from "./app";
        
        ReactDOM.render(<App />, document.getElementById("root"));
        ```
        
        - in app.jsx have all the connections with all the elements
        
        ```jsx
        import React from "react";
        import Header from "./Header";
        import Footer from "./Footer";
        import Note from "./Note";
        
        function App(){
         return <div>
          <Header/>
          <Note/>
          <Footer/>
         </div>
        }
        
        export default App;
        ```
        
    - 013 Javascript ES6 - Import, Export and Modules
        
        - export one with
            - `export default App;`
            - and use it with any name `import App from "./component/App";`
        - else export many functions with
            - `export { add, multiply, subtract, divide };`
            - and use with `import { add, multiply } from "./calculator";` what are needed or all
		- import all the functions of js with `import * as variable from "./functions.js"`
		```js
		import * as pi from "./math.js";
		import pi, {doublrPi, triplePi} from "./math.js";
		```

    - 015 [Windows] 8203 Local Environment Setup for React Development
        
        - Node is upto date
        - VSCode
        - create React App
            - `npx create-react-app app-name`
            - `cd app-name`
            - `npm start`
    - 019 React Props
        
        - for repetitive elements. with function (Capital)
        - change its properties or data with `props` with `name=”harsh”` in `<Card />` as `<Card name=”harsh”/>`
        - you can use its property with `props.name`
    - 021 React DevTools
		- To view all the props which are used and is easier to debug.
        **[React Developer Tools](https://chrome.google.com/webstore/detail/react-developer-tools/fmkadmapgofadopljbjfkapdkoienihi?hl=en)**
        
    - 022 Mapping Data to Components
        - function inception (its a functional programming).
        - `array.map(function createItem(item) { return (<html>) })`
        - all needs a key attribute which is unique. It is not a prop
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
    - 027 React Conditional Rendering with the Ternary Operator & AND Operator
        
        - instead to if else use **Ternary Operator**
        - **CONDITION ? DO IF TRUE : DO IF FALSE**
        - `name=”harsh” ? “Hello Harsh” : null`
        - **CONDITION && DO IF TRUE**
        - `name=”harsh” && “Hello Harsh”`
    - 029 State in React - Declarative vs. Imperative Programming
        - Previously we used **Imperative Programming** this is **Declarative Programming**.
        - Imperative better for UI UX
    - 030 React Hooks - useState
        - `let [variable, setVeriable] = React.usestate(0)`
	        - `setVeriable` is a function
        - `setVeriable(3)` to update the variable
        - for change in the site to update it.
    - 032 Javascript ES6 Object & Array Destructuring
	    - Array Destructuring
		    - From `const cat = animals[0]`
		    - to `const [cat, dog] = animals`
			- the variable names doesn't matter.
	    - Object Destructuring
		    - From `name = cat["name"];`
		    - To `const {name, sound} = cat;`
		    - here the variable name needs to be same as present in JS object
		    - to have different variable names:
			    - `const {name: n, sound: catSound} = cat;
			- what if any internal object we are calling such as `sound` is not defined and need alternative output:
				- `const {name: n, sound: catSound} = cat;
	- Event Handling in React
		- `<button onClick={this.handleClick}>Click me</button>`
	```js
	handleClick(event) {
	  console.log('Button clicked');
	  console.log('Event: ', event);
	}
	```
	
	```js
	import React, { useState } from 'react';
	
	function MyComponent() {
	  // Declare a state variable for tracking click count
	  const [count, setCount] = useState(0);
	
	  // Event handler function for button click
	  const handleClick = () => {
	    setCount(count + 1); // Update the count state
	  };
	
	  return (
	    <div>
	      <p>Clicked {count} times</p>
	      {/* Attach the handleClick function to the button's onClick event */}
	      <button onClick={handleClick}>Click me</button>
	    </div>
	  );
	}
	
	export default MyComponent;
	
	```
	- React Forms
		- `inChange(function)`
			- the function can use attribute `event`
			- and use the changes dome by the user like `event.target.value`
		- use controlled component. have single variable which is being changes.
		- if using `<form>` then use `onSubmit={(event) => event.preventDefault()}`
	- Class Components vs. Functional Components
		- Functional Components is new
		- Synthetic Events (not real events and are created by React)
	- Spread Operator
		- to add another array: `array = [1, 2, 3, ...anotherArray]`
		- can be used at objects: `const user = {...fullName, if: 1, username: "harshrb2424" }`
		- for using `{name: "Harshrb"}` where name is a variable got may be `fillName` it wont work.
			- use `{[name]: "Harshrb"}` which will work as `{fillName: "Harshrb"}`
	- For good CSS
		- https://mui.com/
		- `npm install @mui/icons-material @mui/material @emotion/styled @emotion/react`