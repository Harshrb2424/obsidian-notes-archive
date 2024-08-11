# Design Concepts

M.A Jackson once said: "The beginning of wisdom for a software engineer is to recognize the difference between getting a program to work, and getting it right." Fundamental software design concepts provide the necessary framework for "getting it right."

## Abstraction

Many levels of abstraction exist. At the highest level, a solution is stated in broad terms using the language of the problem environment. Procedural abstraction refers to a sequence of instructions with specific and limited functions, while data abstraction is a named collection of data that describes a data object. Abstraction is crucial for providing a detailed description of the solution at different levels.

## Architecture

Software architecture alludes to "the overall structure of the software and the ways in which that structure provides conceptual integrity for a system." It includes the organization of program components, their interaction, and the structure of data used by these components. The goal is to derive an architectural rendering of a system, serving as a framework for detailed design activities. Different models, such as structured models, framework models, dynamic models, process models, and functional models, can represent architectural design.

## Patterns

Design patterns, defined by Brad Appleton, are "named nuggets of insight that convey the essence of a proven solution to a recurring problem within a certain context amidst competing concerns." Each design pattern describes a structure that solves a specific problem within a context and helps determine its applicability, reusability, and suitability as a guide for similar patterns.

## Modularity

Software architecture and design patterns embody modularity, dividing software into separately named and addressable components or modules. Modularity is crucial for making software intellectually manageable. The "divide and conquer" strategy, breaking a complex problem into manageable pieces, aids in the development, testing, debugging, and maintenance of software. The balance between under-modularity and over-modularity is essential.

## Information Hiding

The principle of information hiding suggests that modules should be "characterized by design decisions that hide from all others." Modules should be specified and designed so that information within a module is inaccessible to other modules that do not need such information. Information hiding aids effective modularity and provides benefits during testing and software maintenance.

## Functional Independence

Functional independence is achieved through effective modularity, abstraction, and information hiding. Modules should have a single-minded function and minimal interaction with other modules. Cohesion and coupling are qualitative criteria for assessing functional independence. Cohesion measures the relative functional strength of a module, and coupling measures the interdependence among modules. Striving for low coupling and high cohesion results in software that is easier to understand and less prone to errors.

## Refinement

Stepwise refinement is a top-down design strategy, proposed by Niklaus Wirth, where a program is developed by successively refining levels of procedural detail. Refinement is a process of elaboration, starting with a high-level statement of function and progressively providing more detail. Abstraction and refinement are complementary concepts that aid the designer in creating a complete design model as the design evolves.


# Refactoring

Refactoring is a reorganization technique that simplifies the design of a component without changing its function or behavior. Fowler defines refactoring as the process of changing a software system in such a way that it does not alter the external behavior of the code yet improves its internal structure. During refactoring, the existing design is examined for redundancy, unused design elements, inefficient or unnecessary algorithms, poorly constructed or inappropriate data structures, or any other design failure that can be corrected to yield a better design. The result is software that is easier to integrate, test, and maintain.

# Design Classes

The software team must define a set of design classes that:

1. **Refine the Analysis Classes:** Provide design details that enable the classes to be implemented.
2. **Create a New Set of Design Classes:** Implement a software infrastructure to support the design solution.

## Types of Design Classes

1. **User Interface Classes:** Define abstractions necessary for human-computer interaction. Often, High-Level Classes (HCL) occur within the context of a metaphor, and the design classes for the interface may be visual representations of the elements of the metaphor.

2. **Business Domain Classes:** Refine analysis classes and identify attributes and services required to implement elements of the business domain.

3. **Process Classes:** Implement lower-level business abstractions required to fully manage business domain classes.

4. **Persistent Classes:** Represent data stores that will persist beyond the execution of the software.

5. **System Classes:** Implement software management and control functions that enable the system to operate and communicate within its computing environment and with the outside world.

As the design model evolves, the software team must develop a complete set of attributes and operations for each design class, reducing the level of abstraction as each analysis class is transformed into a design representation.

## Well-Formed Design Class Characteristics

1. **Complete and Sufficient:** A design class should be the complete encapsulation of all attributes and methods necessary for the class, ensuring sufficiency without unnecessary elements.

2. **Primitiveness:** Methods associated with a design class should be focused on accomplishing one service for the class. Redundant methods for the same purpose should be avoided.

3. **High Cohesion:** A cohesive design class has a small, focused set of responsibilities and single-mindedly applies attributes and methods to implement those responsibilities.

4. **Low Coupling:** Collaboration between design classes should be kept to an acceptable minimum. The law of Demeter suggests that a method should only send messages to methods in neighboring classes, reducing system complexity.