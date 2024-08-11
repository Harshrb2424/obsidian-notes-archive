Software design is an iterative process through which requirements are translated into a "blueprint" for constructing the software.

## Goals of Design

McGlaughlin suggests three characteristics that serve as a guide for the evaluation of good design:

1. The design must implement all explicit requirements contained in the analysis model and accommodate implicit requirements desired by the customer.
2. The design must be a readable, understandable guide for those generating code and for those testing and subsequently supporting the software.
3. The design should provide a complete picture of the software, addressing the data, functional, and behavioral domains from an implementation perspective.

## Quality Guidelines

In order to evaluate the quality of a design representation, technical criteria for good design are established:

- A design should exhibit an architecture that
  - has been created using recognizable architectural styles or patterns
  - is composed of components that exhibit good design characteristics and can be implemented in an evolutionary fashion, thereby facilitating implementation and testing.
- A design should be modular; that is, the software should be logically partitioned into elements or subsystems.
- A design should contain a distinct representation of data, architecture, interfaces, and components.
- A design should lead to data structures that are appropriate for the classes to be implemented and are drawn from recognizable data patterns.
- A design should lead to components that exhibit independent functional characteristics.
- A design should lead to interfaces that reduce the complexity of connections between components and with the external environment.
- A design should be derived using a repeatable method driven by information obtained during software requirements analysis.
- A design should be represented using a notation that effectively communicates its meaning.

These design guidelines are not achieved by chance. Design engineering encourages good design through the application of fundamental design principles, systematic methodology, and thorough review.

## Quality Attributes

The FURPS quality attributes represent a target for all software design:

- **Functionality**: Assessed by evaluating the feature set, capabilities of the program, generality of functions, and security of the overall system.
- **Usability**: Assessed by considering human factors, overall aesthetics, consistency, and documentation.
- **Reliability**: Evaluated by measuring the frequency and severity of failure, accuracy of output results, mean-time-to-failure (MTTF), ability to recover from failure, and predictability of the program.
- **Performance**: Measured by processing speed, response time, resource consumption, throughput, and efficiency.
- **Supportability**: Combines the ability to extend the program (extensibility), adaptability, serviceability; these three attributes represent a more common term, maintainability.

Not every software quality attribute is weighted equally as the software design is developed. One application may stress functionality with a special emphasis on security, another may demand performance with particular emphasis on processing speed, and a third might focus on reliability.