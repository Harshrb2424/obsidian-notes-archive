**Introduction to DBANK (Inspired by Compound)**

- Overview of the project: Building a decentralized finance (Defi) app called DBANK inspired by Compound protocol.
- Explanation of Compound protocol: A money market protocol enabling lending and borrowing of tokens with interest.
- Objective: Writing code to earn interest on token balances using Motoko programming language.

**Understanding Motoko**

- Introduction to Motoko: A programming language designed for Internet Computer Smart contracts by the Dfinity team.
- Origin and design: Created by Andreas Rossberg, co-creator of WebAssembly, with a focus on modernity and versatility.
- Similarities with other languages: Resemblance to popular languages like JavaScript, Swift, TypeScript, C#, and Java, making it adaptable for programmers.
- Importance of adaptability: Emphasizes the necessity for programmers to quickly learn and adapt to new languages and paradigms.

**Getting Started**

- Next steps: Transitioning to learning about Motoko and initiating the process of building a decentralized application on the Internet Computer (ICP).

# Introduction to Motoko Language for Internet Computer Development

## Creating a New Project

To initiate project development for the Internet Computer, we create a new project using the dfx SDK. Navigate to the project directory (`ic-projects`) and execute the following command:

```bash
cd ic-projects
dfx new dbank
```

This creates a new project named "dbank" for building a decentralized finance (Defi) application.

## Setting Up the Project Structure

After creating the project, we can explore its structure:

- `README`: Contains project information and instructions.
- `.git`: Git configuration for version control.
- `src`: Folder where the main code resides.
- `node_modules`: Contains dependencies.

Open the project in your preferred code editor (e.g., VS Code) for further development.

## Understanding Motoko Syntax

The main file for our project is `main.mo`. Let's delete the pre-existing code and start fresh. We'll create an actor class named "DBank" to encapsulate canister functionalities:

```java
actor DBank {

}
```

## Variables and Constants in Motoko

Variables and constants in Motoko are declared using `var` and `let` keywords, respectively. Here's an example:

```java
var currentValue : Nat := 300; // Variable declaration and initialization
let id : Nat = 12345; // Constant declaration
```

Ensure to distinguish between variables and constants based on mutability requirements.

## Utilizing Debugging Tools

Motoko provides a Debug module for debugging purposes. We can use the `print` function to output text or values during local development:

```java
import Debug "mo:base/Debug";

Debug.print("Hello, world!");
```

For printing values, use `debug_show` function:

```java
Debug.debug_show(currentValue);
```

## Challenge and Conclusion

Take an active role in learning by attempting challenges. Try printing the value stored in the constant `id` using `debug_show` function. Review the covered material to prepare for the next lesson on enhancing the `dbank` project.

# Motoko Functions and the Candid User Interface

## Creating Functions
To enable users to deposit funds into our application, we create a function named `topUp` within our actor class (`DBank`). Functions in Motoko are declared using the `func` keyword followed by the function name and its body enclosed in curly brackets. For instance:
```java
actor DBank {
    func topUp() {
        currentValue += 1; // Incrementing currentValue by $1
    }
}
```

## Debugging and Testing
We incorporate debugging techniques using the `Debug.print` function to verify the updated value of `currentValue` after each function call. Additionally, we experiment with calling the function from the command line interface (`dfx canister call`) and observe the results.

## Making Functions Public
To make the `topUp` function accessible externally, we declare it as `public`. This allows interaction with the function through the Candid user interface, simplifying testing and debugging processes.

## Utilizing the Candid User Interface
The Candid user interface provides an intuitive way to interact with canister functions without directly using the command line interface. By accessing the Candid UI, users can trigger functions and observe their effects, facilitating development and testing.

## Challenge: Implementing a Withdrawal Function
As a challenge, we task ourselves with creating a `withdrawal` function that decrements the `currentValue` by a specified amount. We ensure to handle inputs appropriately and print the updated value for verification.

# Motoko Conditionals and Type Annotations

## Implementing Conditional Statements
To prevent the underflow error, we utilize an if-statement to check if the subtraction operation would result in a non-negative value. If the condition is met, we perform the subtraction and print the updated value. Otherwise, we handle the error by printing a debug message.

```java
actor DBank {
    func withdrawal(amount : Nat) {
        if (currentValue - amount) >= 0 {
            let tempValue : Int = currentValue - amount;
            currentValue = tempValue;
            Debug.print("Current value after withdrawal: ", currentValue);
        } else {
            Debug.print("Amount too large; currentValue less than 0");
        }
    }
}
```

## Handling Type Inference and Annotations
While implementing the subtraction operation, Motoko may infer ambiguous types, leading to potential errors. To address this, we explicitly annotate the type of the result of the subtraction operation (`tempValue`) as `Int`, ensuring clarity and avoiding type inference issues.

## Testing the Functionality
We verify the functionality of the `withdrawal` function by testing it with both reasonable and large withdrawal amounts. The conditional statements ensure that withdrawals are executed successfully without causing underflow errors.

# Query vs Update Methods

## Introduction
In the previous lessons, we observed a delay when executing functions like `topUp` and `withdrawal` due to their nature as update methods. In this lesson, we'll explore the concept of query and update methods in the context of Internet Computer canisters, and how they differ in terms of execution time and impact on the blockchain.

## Understanding Query and Update Methods
Update methods, such as `topUp` and `withdrawal`, are responsible for modifying the state of variables within a canister. These operations involve writing to the blockchain and are computationally expensive, resulting in longer execution times.

In contrast, query methods enable users to retrieve the current state or data from a canister without altering it. These methods are optimized for read-only operations and execute much faster compared to update methods.

## Implementing Query Methods
To create a query method in Motoko, we use the `query` keyword before the `func` keyword to indicate that the function is a query method. We define the function to return the desired data type asynchronously, ensuring quick retrieval of information without modifying the state of the canister.

```java
actor DBank {
    query func checkBalance() : async Nat {
        return currentValue;
    }
}
```

## Testing Query Method Performance
Upon deploying the updated canister with the `checkBalance` query method, we observe its execution time to be significantly faster compared to update methods like `topUp` and `withdrawal`. Query methods provide a rapid means of accessing canister state for read-only operations, enhancing user experience and efficiency.

# Tracking Time and Calculating Compound Interest

## Understanding Compound Interest
Compound interest is a powerful concept in finance where the interest earned on an investment is added to the principal amount, resulting in the interest earning interest over time. This exponential growth is a fundamental principle of investment and wealth accumulation.

## Compound Interest Formula
The compound interest formula calculates the future value of an investment based on the initial principal, interest rate, and time period. The formula is expressed as:

$A = P \times (1 + r/n)^{nt}$

Where:
- \( A \) is the future value of the investment
- \( P \) is the principal amount (initial investment)
- \( r \) is the annual interest rate (in decimal form)
- \( n \) is the number of times interest is compounded per unit of time
- \( t \) is the time the money is invested for, in years

## Implementing Compound Interest in Motoko
To implement compound interest in Motoko, we first need to track time using the `Time` module to calculate the elapsed time since the investment was made. Then, we use the compound interest formula to compute the new value of the investment based on the elapsed time and the specified interest rate.

```java
import Time "mo:base/Time";

actor CompoundProtocol {
    stable var currentValue : Float = 300.0; // Initial investment
    stable var startTime : Time = Time.now(); // Start time of the investment
    
    public func compound() {
        let currentTime : Time = Time.now();
        let timeElapsedNS : Int = currentTime - startTime;
        let timeElapsedS : Float = Float.fromInt(timeElapsedNS) / 1_000_000_000.0; // Convert nanoseconds to seconds
        
        // Calculate compound interest
        let interestRate : Float = 0.01; // 1% interest rate per second
        currentValue := currentValue * (1.0 + interestRate) ** timeElapsedS;
        
        // Reset start time for future compound calculations
        startTime := currentTime;
    }
}
```

## Testing Compound Interest
To test compound interest, we can deploy the canister and invoke the `compound` function to see how the investment grows over time. Each time the `compound` function is called, the value of the investment will increase based on the elapsed time and the specified interest rate.

Implementing compound interest in Motoko allows us to simulate the growth of investments over time. By understanding the compound interest formula and leveraging Motoko's features, we can build powerful financial applications on the Internet Computer blockchain.

Experiment with different interest rates and time periods to see how compound interest impacts investment growth, and continue exploring the capabilities of Motoko to build innovative decentralized finance applications.


# Adding HTML and CSS to Create the Frontend for DBANK

## Introduction
In this lesson, we focus on creating the frontend for our decentralized finance (DeFi) application, DBANK. We'll replace the default template with custom HTML and CSS files to design the user interface.

## Deleting Default Template
We start by deleting the default assets generated by the ICP template, including `index.html`, `main.css`, and `index.js`, to make room for our custom frontend code.

## Implementing Custom Frontend
1. **Downloading Frontend Files**:
    - Download the `index` and `main` files from the course resources.
    - Copy the content of these files into `index.html` and `main.css` respectively.
    
2. **Understanding Frontend Code**:
    - Review the HTML and CSS code to understand the structure and styling of the frontend components.
    - The HTML code includes elements for the logo, current balance display, input fields for deposit and withdrawal, and a submit button.
    - CSS code styles these elements to create a visually appealing layout.
    
3. **Updating Logo**:
    - Download the custom logo for DBANK from the course resources.
    - Replace the default logo in the assets folder with the custom logo.
    
4. **Viewing Frontend**:
    - Run `npm install` to install required packages.
    - Start the local Internet Computer using `dfx start`.
    - Deploy the canister using `dfx deploy`.
    - Start the web server with `npm start` to view the frontend.
    - Verify that the frontend layout is displayed correctly, though the logo may be missing.

# Connecting the Motoko Backend to our JS Frontend

## Introduction
In this lesson, we focus on integrating the Motoko backend with the JavaScript frontend to enable interaction between the two components of our decentralized finance application, DBANK. We cover importing the dbank module, updating the frontend based on backend data, handling user inputs for top-up and withdrawal, and implementing input validation.

## Importing dbank Module
- We import the dbank module in our index.js file to access backend functionalities.
- The dbank module is located in the declarations folder and acts as a bridge between Motoko and JavaScript.

## Updating Frontend Based on Backend Data
- We use JavaScript to update the frontend with current balance fetched from the backend using checkBalance() function.
- An event listener for the 'load' event is added to update the balance when the page loads.

## Handling User Inputs for Top-Up and Withdrawal
- We add event listeners to the form submit button to handle top-up and withdrawal transactions.
- JavaScript functions are used to fetch input values, call backend functions, and update the frontend accordingly.

## Implementing Input Validation
- Input validation is implemented to prevent errors when submitting empty input fields.
- Conditional statements are used to check if input fields are empty before triggering backend functions.

## Enhancing User Experience
- Disabled attribute is applied to the submit button during transaction processing to prevent multiple submissions.
- Input fields are cleared after transaction completion for a better user experience.

## Compounding Interest
- We add functionality to compound interest after each transaction, updating the current balance accordingly.

## Refactoring Code
- Code refactoring is performed to improve readability and reduce redundancy.
- Repeated code for updating the frontend is moved to a separate async function called 'update()'.

