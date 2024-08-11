- **Adding Javascript** to Websites
    
    ```
    <!-- In Line JS -->
      <body onload="alert('In Line Hello');">
    
    <!-- Internal JS -->
    <script type="text/javascript">
    alert('Internal Hello');
    </script>
    
    <!-- External JS -->
    <script src="index.js"></script>
    ```
- Introduction to the Document Object Model **(DOM)**
    
    ```jsx
    document.firstElementChild.lastElementChild.lastElementChild.lastElementChild.innerHTML = "harsh";
    
    document
    	HTML - firstElementChild
    				Head - firstElementChild
    				Body - lastElementChild
    							H1 - firstElementChild
    ```
    
    - Element Has
        - Properties
            - .innerHTML;
            - .style;
            - .firstChild;
        - Methods
            - click( )
            - appendChild( );
            - setAttribute( );
        - Selector
            - querySelector();
            - querySelectorAll() gives array
            - .getElementsByTagName(); gives array
            - getElementsByClassName(); gives array
            - getElementById();
    - Array
        - `var array = [”Harsh”, ”R”, ”B”]`
        - `array[0]` gives 1st element in array
        - `array.length` gives number of elements in it.
        - `Array.prototype.push()` or `pop()` to add or remove an element
- Selecting HTML Elements with Javascript - **querySelector("button");**
    
    - `document.getElementsByTagName("button")` Can select any number of elements in Arrey.
        - `getElementsByTagName("button")[0]` to select the 1st element.
        - example `document.getElementsByTagName("button")[0].style.color = "blue";`
    - `document.getElementsByClassName("list");` can select list of items in Class.
    - `document.getElementById("top");` can select items in an id.
    - `document.querySelector("button");` Can select any one (First) element `h1`, class `.main`, id `#top`.
    - `document.querySelectorAll("button");` Can select any list of items in element `h1`, class `.main`, id `#top`.
- 05 Manipulating and Changing Styles of HTML Elements with Javascript - **.style.backgroundColor**
    
    - Changing Styles in JS use same elements but in camel casing.
    - Example `document.querySelector("button").style.backgroundColor = "aqua";`
- 06 The Separation of Concerns_ Structure vs Style vs Behaviour - **.classList**
    
    - `document.querySelector("li").classList` to see the class in the element in array
    - `document.querySelector("li").classList.add`, `.remove` and `.toggle` to add, remove and toggle classes for an element.
- 07 Text Manipulation and the Text Content Property -**.innerHTML;** **.textContent;**
    
    - `document.querySelector("h1").textContent;` to select contents of Text eliminating html code if any inside.
        - u can change by using `.textContent= "I have changed!";`
    - `document.querySelector("h1").innerHTML;` to select contents of text with html code if any inside.
        - u can change by using `.innerHTML = "<em>I have changed!</em>";`
- 08 Manipulating HTML Element Attributes **.attributes**
    
    - `document.querySelector("a").attributes;` get array of attributes present in an element.
    - `document.querySelector("a").getAttribute("href");` get info in a particular attribute in an element.
    - `document.querySelector("a").setAttribute("href", "[<https://www.bing.com>](<https://www.bing.com/>)");` change a particular attribute in an element.


- 01-03 **Adding Event Listeners**
    
    - `addEventListener(type, listener);`
        - example
            
            ```
            document.querySelectorAll("button")[count].addEventListener("click", click);
            function click(){
                    console.log(this.innerHTML)
                    outputAudio(this.innerHTML)
                    animation(this.innerHTML) 
            }
            
            document.addEventListener("keydown", function(){
                console.log(key.key)
                outputAudio(key.key)
                animation(key.key)
            })
            ```
- 004 **Higher Order Functions** And Passing Functions as Arguments
    
    - Calculater example - u can call other function (add, sub, multiply) in other function (calculater)
        - calculater(5,12,add) → add(5,12) → 5+12 → 17
- 004 **Debugger**
    
    - `debugger;`
        
        `function();` to Debug how it works.
- 006 How to **Play** Sounds on a Website - **audio.play();**
    
    - `var audioo = new Audio('sounds/tom-3.mp3');` creates a variable which can play audio
        - `audioo.play();` plays the audio
    - `this` refers to the **object.**
        - In a function, `this` refers to the **global object**.
- 007 A Deeper Understanding of Javascript Objects - **Variable (multi)**
    
    - a variable can have more information
        
        - `var Car = {`
        
        `company: "Audi",`
        
        `model: "e tron gt"`
        
        `}` u can call them my `Car.company` , `Car.model` .
        
    - **Constructors Function**
        
        - creates a **Constructors Function**
            - function names has an upper case in 1st letter.
        
        ```jsx
        function Person(first, last, age, eye) {
          this.firstName = first;
          this.lastName = last;
          this.age = age;
          this.eyeColor = eye;
        }
        ```
        
        - use it to create variables
            - `car Person2 = new Person(first, last, age, eye) ;`
- 008 How to Use **Switch** Statements in Javascript
    
    - `key` is the input to look and switch accordingly
    - `value` = `key` it will we triggered
    - `default` is line Else statement
    
    ```
    switch (key) {
            case value:
                //what to do
                break;
            case value:
                //what other thing to do
                break;
        
            default:
                break;
        }
    ```
- 009 Objects, their Methods and the Dot Notation - **Functions (multi)**
    
    - A Constructors Function can have other function in what can be called with `**this.finction()**`
- 011 Using Keyboard Event Listeners to Check for Key Presses - **.addEventListener('keypress', function);**
    
    - `addEventListener` with type `keypress`
    
    ```jsx
    input.addEventListener('keypress', logKey);
    
    function logKey(e) {
      log.textContent += ` ${e.code}`;
    }
    ```
- 012 Understanding Callbacks and How to Respond to Events - **addEventListener("click", function)**
    
    - Callbacks
    - `$0.addEventListener("click", function(e) {`
    
    `console.log(e);`
    
    `})` extract info how it happened.
- 013 Adding Animation to Websites - **setTimeout**
    
    - add class to emulate click visually
        
    - remove the class after 200ms
        
        - `setTimeout( function( ){ } , ms )`
        
        ```
        setTimeout(
                function(){
        //function
                    document.querySelector("."+inputAni).classList.remove("pressed")
        //delay = 200ms
                }, 200)
        ```
