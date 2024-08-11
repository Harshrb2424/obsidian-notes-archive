# Unit 1
### 1. **Need for OOP Paradigm**
   - Code Reusability
   - Modular Design
   - Maintainability
   - Flexibility
   - Real-world Modeling

### 2. **Summary of OOP Concepts**
   - **Encapsulation**
     - Data Hiding
     - Access Modifiers
   - **Inheritance**
     - Base Class
     - Derived Class
   - **Polymorphism**
     - Method Overloading
     - Method Overriding
   - **Abstraction**
     - Abstract Classes
     - Interfaces

### 3. **Coping with Complexity**
   - Decomposition
   - Modularity
   - Encapsulation
   - Hierarchical Structuring

### 4. **Abstraction Mechanisms**
   - Abstract Classes
   - Interfaces
   - Abstract Methods

### 5. **Agents, Responsibility, Messages, Methods**
   - **Agents**: Objects
   - **Responsibility**: Tasks/Behaviors
   - **Messages**: Method Calls
   - **Methods**: Operations

### 6. **History of Java**
   - **Origin**: Sun Microsystems
   - **Released**: 1995
   - **Creators**: James Gosling, Mike Sheridan, Patrick Naughton

### 7. **Java Buzzwords**
   - Simple
   - Object-Oriented
   - Distributed
   - Networked
   - Robust
   - Secure
   - Architecture-Neutral
   - Portable
   - High-Performance
   - Multithreaded
   - Dynamic

### 8. **Data Types**
   - Primitive Types: byte, short, int, long, float, double, char, boolean
   - Reference Types: Objects, Arrays

### 9. **Variables**
   - Local Variables
   - Instance Variables
   - Class Variables (Static)

### 10. **Scope and Lifetime of Variables**
   - **Local Variables**: Method Scope, Temporary Lifetime
   - **Instance Variables**: Object Scope, Lifetime tied to object
   - **Class Variables**: Class Scope, Lifetime tied to class

### 11. **Arrays**
   - Single-Dimensional Arrays
   - Multi-Dimensional Arrays
   - Array Declaration, Initialization

### 12. **Operators**
   - Arithmetic Operators
   - Relational Operators
   - Logical Operators
   - Assignment Operators
   - Unary Operators

### 13. **Expressions**
   - Arithmetic Expressions
   - Relational Expressions
   - Logical Expressions

### 14. **Control Statements**
   - **Decision Making**: if, else, switch
   - **Loops**: for, while, do-while
   - **Branching**: break, continue

### 15. **Type Conversion and Casting**
   - **Implicit Conversion**: Widening
   - **Explicit Conversion**: Narrowing
   - **Casting**: Type Casting

### 16. **Simple Java Program**
   - **Structure**: Class, Main Method, Statements
   - **Example**: `public class Main { public static void main(String[] args) { System.out.println("Hello, World!"); } }`

### 17. **Concepts of Classes and Objects**
   - **Class**: Blueprint for Objects
   - **Object**: Instance of a Class

### 18. **Constructors**
   - **Default Constructor**
   - **Parameterized Constructor**
   - **Constructor Overloading**

### 19. **Methods**
   - **Definition**: Function in a Class
   - **Method Overloading**
   - **Method Signature**
   - **Return Type**

### 20. **Access Control**
   - **Modifiers**: public, private, protected
   - **Default Access**

### 21. **This Keyword**
   - Refers to Current Object
   - Accessing Instance Variables
   - Calling Other Constructors

### 22. **Garbage Collection**
   - Automatic Memory Management
   - **GC Mechanisms**: Reference Counting, Mark-and-Sweep

### 23. **Overloading Methods and Constructors**
   - **Method Overloading**: Same Name, Different Parameters
   - **Constructor Overloading**: Different Constructors in a Class

### 24. **Method Binding**
   - **Early Binding**: Compile-Time
   - **Late Binding**: Runtime

### 25. **Inheritance**
   - **Types**: Single, Multi-Level, Hierarchical
   - **Base and Derived Classes**

### 26. **Overriding and Exceptions**
   - **Method Overriding**: Redefining in Subclass
   - **Exceptions**: try, catch, throw, throws, finally

### 27. **Parameter Passing**
   - **Pass by Value**: Primitive Types
   - **Pass by Reference**: Objects

### 28. **Recursion**
   - **Definition**: Function Calling Itself
   - **Base Case**
   - **Recursive Case**

### 29. **Nested and Inner Classes**
   - **Nested Classes**: Static and Non-Static
   - **Inner Classes**: Member Classes, Local Classes, Anonymous Classes

### 30. **Exploring String Class**
   - **Methods**: length(), charAt(), substring(), indexOf(), equals(), toLowerCase(), toUpperCase()
   - **Immutability**

---
# Unit 2
### 1. **Inheritance**
   - **Hierarchical Abstractions**: Organizing classes in a hierarchy.
   - **Base Class Object**: The superclass from which other classes inherit.
   - **Subclass**: A class that inherits from another class.
   - **Subtype**: A class that conforms to the type of its superclass.
   - **Substitutability**: Subclasses can be used in place of their base class.
   - **Forms of Inheritance**:
     - **Single Inheritance**: A class inherits from one superclass.
     - **Multilevel Inheritance**: A class inherits from another class, which in turn inherits from another class.
     - **Hierarchical Inheritance**: Multiple classes inherit from a single superclass.
     - **Multiple Inheritance** (through interfaces): A class implements multiple interfaces.
   - **Specialization**: Subclass adds specific details to the general behavior of the base class.
   - **Specification**: Subclass defines more detailed behaviors and constraints.
   - **Construction**: Using constructors to initialize the subclass.
   - **Extension**: Adding new methods and fields in the subclass.
   - **Limitation**: Restricting or overriding behaviors from the base class.
   - **Combination**: Using a mix of inheritance and other OOP concepts.
   - **Benefits of Inheritance**:
     - Code Reusability
     - Improved Maintainability
     - Hierarchical Organization
   - **Costs of Inheritance**:
     - Complexity
     - Tight Coupling
     - Fragile Base Class Problem
   - **Member Access Rules**: Access to superclass members (public, protected, private).
   - **Super Uses**:
     - Accessing superclass methods: `super.method()`
     - Calling superclass constructor: `super()`
   - **Using `final` with Inheritance**:
     - **Final Classes**: Cannot be subclassed.
     - **Final Methods**: Cannot be overridden.
     - **Final Variables**: Constants.

### 2. **Polymorphism**
   - **Method Overriding**: Redefining a method in a subclass with the same signature.
   - **Dynamic Method Dispatch**: Runtime method binding.

### 3. **Abstract Classes**
   - **Definition**: Classes that cannot be instantiated and may contain abstract methods.
   - **Abstract Methods**: Methods without implementation in the abstract class.

### 4. **The Object Class**
   - **Base Class**: All classes inherit from `Object`.
   - **Common Methods**: `equals()`, `hashCode()`, `toString()`, `clone()`, `getClass()`

### 5. **Packages**
   - **Defining a Package**: Using `package` keyword.
   - **Creating a Package**: Organizing related classes.
   - **Accessing a Package**: Using `import` statements.
   - **Understanding CLASSPATH**: Location for Java classes and packages.
   - **Importing Packages**: `import package.name.ClassName;` or `import package.name.*;`

### 6. **Interfaces**
   - **Differences between Classes and Interfaces**:
     - **Classes**: Can have implementation, can inherit from one class.
     - **Interfaces**: Cannot have implementation (until Java 8), can be implemented by multiple classes.
   - **Defining an Interface**: Using `interface` keyword.
   - **Implementing Interface**: Using `implements` keyword.
   - **Applying Interfaces**: To provide multiple behaviors.
   - **Variables in Interface**: Implicitly `public`, `static`, and `final`.
   - **Extending Interfaces**: Using `extends` keyword, multiple interfaces.

### 7. **Exploring `java.io`**
   - **Streams**: Input and Output Streams.
   - **File Handling**: Reading from and writing to files.
   - **Serialization**: Converting objects to a byte stream.
   - **Exceptions**: Handling I/O related exceptions.

---
# Unit 3
### 1. **Exception Handling**
   - **Concepts of Exception Handling**:
     - **Exception**: An event that disrupts the normal flow of execution.
     - **Error**: A severe problem that typically cannot be handled.
   - **Benefits of Exception Handling**:
     - **Error Detection**: Helps in detecting runtime errors.
     - **Separation of Error Handling Code**: Keeps error handling separate from normal code.
     - **Improved Reliability**: Allows programs to handle errors gracefully.
   - **Termination or Resumptive Models**:
     - **Termination Model**: Aborts execution when an exception occurs.
     - **Resumptive Model**: Continues execution after handling an exception.
   - **Exception Hierarchy**:
     - **Throwable**: Base class for all exceptions and errors.
       - **Exception**: For checked exceptions.
         - **IOException**
         - **SQLException**
       - **RuntimeException**: For unchecked exceptions.
         - **NullPointerException**
         - **ArithmeticException**
     - **Error**: For serious issues not intended to be caught.
   - **Usage of `try`, `catch`, `throw`, `throws`, and `finally`**:
     - **`try`**: Block of code to be monitored for exceptions.
     - **`catch`**: Block to handle exceptions thrown by `try`.
     - **`throw`**: Used to explicitly throw an exception.
     - **`throws`**: Indicates that a method can throw exceptions.
     - **`finally`**: Block executed regardless of whether an exception occurs or not.
   - **Built-in Exceptions**:
     - **ArithmeticException**: Division by zero.
     - **ArrayIndexOutOfBoundsException**: Invalid array index.
     - **ClassNotFoundException**: Class not found.
     - **FileNotFoundException**: File not found.
   - **Creating Own Exception Subclasses**:
     - **Custom Exceptions**: Extend `Exception` or `RuntimeException`.
     - **Define Constructors**: For custom messages and cause.

### 2. **String Handling**
   - **String Class**: Immutable sequences of characters.
   - **Common Methods**:
     - `length()`, `charAt()`, `substring()`, `indexOf()`, `concat()`, `equals()`, `toUpperCase()`, `toLowerCase()`, `trim()`

### 3. **Exploring `java.util`**
   - **Common Classes and Interfaces**:
     - **Collections**: `ArrayList`, `HashSet`, `LinkedList`, `HashMap`
     - **Utilities**: `Collections`, `Date`, `Calendar`, `Random`

### 4. **Differences Between Multithreading and Multitasking**
   - **Multithreading**: Multiple threads within a single process sharing resources.
   - **Multitasking**: Multiple processes running simultaneously, each with its own resources.

### 5. **Thread Life Cycle**
   - **States**:
     - **New**: Thread is created.
     - **Runnable**: Thread is ready to run or running.
     - **Blocked**: Thread is waiting for a resource.
     - **Waiting**: Thread is waiting indefinitely.
     - **Timed Waiting**: Thread is waiting for a specific time.
     - **Terminated**: Thread has completed execution.

### 6. **Creating Threads**
   - **Extending `Thread` Class**: Override `run()` method.
   - **Implementing `Runnable` Interface**: Implement `run()` method and use `Thread` class to start.

### 7. **Thread Priorities**
   - **Priority Levels**: `Thread.MIN_PRIORITY`, `Thread.NORM_PRIORITY`, `Thread.MAX_PRIORITY`
   - **Setting Priority**: `setPriority()`

### 8. **Synchronizing Threads**
   - **Synchronization**: Using `synchronized` keyword to avoid concurrent access issues.
   - **Synchronization Blocks**: Lock specific code sections.

### 9. **Inter-Thread Communication**
   - **Methods**:
     - `wait()`, `notify()`, `notifyAll()`
   - **Usage**: Coordinating thread activities.

### 10. **Thread Groups**
   - **Managing Threads**: Grouping related threads.
   - **Methods**: `activeCount()`, `list()`, `interrupt()`

### 11. **Daemon Threads**
   - **Purpose**: Background threads that do not prevent the JVM from exiting.
   - **Setting**: `setDaemon(true)`

### 12. **Enumerations**
   - **Definition**: A special data type for a set of predefined constants.
   - **Usage**: Define `enum` with constants.

### 13. **Autoboxing**
   - **Automatic Conversion**: Between primitive types and their corresponding wrapper classes (`int` to `Integer`, `double` to `Double`).

### 14. **Annotations**
   - **Metadata**: Adding information to code.
   - **Common Annotations**: `@Override`, `@Deprecated`, `@SuppressWarnings`

### 15. **Generics**
   - **Type Parameters**: Allow classes, interfaces, and methods to operate on specified types.
   - **Usage**: `<T>`, `<E>`, `<K, V>`
   - **Benefits**: Type Safety, Elimination of Casts
---
# Unit 4
### 1. **Event Handling**
   - **Events**: Actions or occurrences detected by the program (e.g., button clicks, key presses).
   - **Event Sources**: Objects that generate events (e.g., buttons, text fields).
   - **Event Classes**: Classes that encapsulate information about events (e.g., `ActionEvent`, `MouseEvent`, `KeyEvent`).
   - **Event Listeners**: Interfaces that handle events by providing methods to respond to specific events (e.g., `ActionListener`, `MouseListener`, `KeyListener`).
   - **Delegation Event Model**: The process of handling events where event sources delegate event handling to event listeners.

### 2. **Handling Mouse and Keyboard Events**
   - **Mouse Events**:
     - **MouseListener**: `mouseClicked()`, `mouseEntered()`, `mouseExited()`, `mousePressed()`, `mouseReleased()`
     - **MouseMotionListener**: `mouseDragged()`, `mouseMoved()`
   - **Keyboard Events**:
     - **KeyListener**: `keyPressed()`, `keyReleased()`, `keyTyped()`

### 3. **Adapter Classes**
   - **Purpose**: Provide default implementations of event listener methods.
   - **Examples**:
     - **`MouseAdapter`**: Implements `MouseListener` and `MouseMotionListener` with empty methods.
     - **`KeyAdapter`**: Implements `KeyListener` with empty methods.
     - **`WindowAdapter`**: Implements `WindowListener` with empty methods.

### 4. **AWT (Abstract Window Toolkit)**
   - **The AWT Class Hierarchy**:
     - **Component**: Base class for all AWT components.
     - **Container**: A type of component that can contain other components (e.g., `Panel`, `Frame`).
     - **Component** → **Container** → **Panel**, **Frame**, **Dialog**
   - **User Interface Components**:
     - **Labels**: `Label` for displaying text.
     - **Button**: `Button` for clickable buttons.
     - **Canvas**: `Canvas` for drawing and painting.
     - **Scrollbars**: `Scrollbar` for scrollable content.
     - **Text Components**:
       - **TextField**: Single-line text input.
       - **TextArea**: Multi-line text input.
     - **Check Box**: `Checkbox` for on/off selections.
     - **Checkbox Groups**: Group of checkboxes with mutually exclusive options (`CheckboxGroup`).
     - **Choices**: `Choice` for drop-down lists.
     - **Lists**: `List` for displaying a list of items.
     - **Panels**: `Panel` for grouping components.
     - **Scrollpane**: `ScrollPane` for adding scrollbars to components.
     - **Dialogs**: `Dialog` for pop-up windows.
     - **Menubar**: `MenuBar` for adding menus to a window.

### 5. **Graphics**
   - **Drawing**: Using `Graphics` class to draw shapes, text, and images.
   - **Methods**: `drawLine()`, `drawRect()`, `drawOval()`, `fillRect()`, `fillOval()`, `drawImage()`

### 6. **Layout Managers**
   - **Border Layout**: Arranges components in five regions: North, South, East, West, Center.
   - **Grid Layout**: Arranges components in a grid of cells.
   - **Flow Layout**: Arranges components in a left-to-right flow.
   - **Card Layout**: Allows switching between multiple components (cards).
   - **GridBag Layout**: Flexible grid-based layout.

---
# Unit 5
### 1. **Applets**
   - **Concepts of Applets**: Small Java programs that run within a web browser.
   - **Differences Between Applets and Applications**:
     - **Applets**:
       - Run in a browser or applet viewer.
       - Require HTML for embedding.
       - Limited access to the system resources for security reasons.
     - **Applications**:
       - Standalone programs.
       - Run directly on the JVM.
       - Have full access to system resources.
   - **Life Cycle of an Applet**:
     - **`init()`**: Called once when the applet is first loaded.
     - **`start()`**: Called each time the applet becomes active.
     - **`stop()`**: Called each time the applet becomes inactive.
     - **`destroy()`**: Called once when the applet is destroyed.
   - **Types of Applets**:
     - **Unsigned Applets**: Have restricted access to system resources.
     - **Signed Applets**: Can request permission to access system resources.
   - **Creating Applets**: Extend the `Applet` or `JApplet` class and override life cycle methods (`init()`, `start()`, `stop()`, `destroy()`).
   - **Passing Parameters to Applets**: Use HTML `param` tags to pass parameters, accessed in the applet using `getParameter()`.

### 2. **Swing**
   - **Introduction**: A GUI toolkit in Java that provides a richer set of components than AWT.
   - **Limitations of AWT**: Limited components, platform-dependent, less flexible.
   - **MVC Architecture**: Model-View-Controller design pattern used in Swing for separating the data model, UI, and control logic.
   - **Components and Containers**:
     - **Components**: Basic building blocks (e.g., buttons, labels).
     - **Containers**: Hold and organize components (e.g., `JFrame`, `JPanel`).

### 3. **Exploring Swing**
   - **JApplet**: A Swing-based applet class.
   - **JFrame**: A top-level window with a title and border.
   - **JComponent**: The base class for all Swing components.
   - **Icons and Labels**: `JLabel` for displaying text and images.
   - **Text Fields**: `JTextField` for single-line text input.
   - **Buttons**: `JButton` for clickable buttons.
   - **Check Boxes**: `JCheckBox` for on/off selections.
   - **Radio Buttons**: `JRadioButton` for mutually exclusive options.
   - **Combo Boxes**: `JComboBox` for drop-down lists.
   - **Tabbed Panes**: `JTabbedPane` for organizing content in tabs.
   - **Scroll Panes**: `JScrollPane` for adding scrollbars to components.
   - **Trees**: `JTree` for displaying hierarchical data.
   - **Tables**: `JTable` for displaying tabular data.

### Example Snippets

#### **Creating a Simple Applet**

```java
import java.applet.Applet;
import java.awt.Graphics;

public class SimpleApplet extends Applet {
    public void paint(Graphics g) {
        g.drawString("Hello, Applet!", 20, 20);
    }
}
```

#### **Creating a Swing Application with JFrame**

```java
import javax.swing.*;

public class SimpleSwingApp {
    public static void main(String[] args) {
        JFrame frame = new JFrame("Simple Swing Application");
        JLabel label = new JLabel("Hello, Swing!");
        
        frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        frame.add(label);
        frame.setSize(300, 200);
        frame.setVisible(true);
    }
}
```

#### **Creating a JApplet**

```java
import javax.swing.*;

public class SimpleJApplet extends JApplet {
    public void init() {
        JLabel label = new JLabel("Hello, JApplet!");
        add(label);
    }
}
```

---