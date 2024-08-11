# Software Requirements

Software requirements are essential to:

- Introduce the concepts of user and system requirements
- Describe functional and non-functional requirements
- Explain how software requirements may be organized in a requirements document

## What is a Requirement?

A requirement for the system entails the description of the services provided by the system and its operational constraints. It can range from a high-level abstract statement of a service or system constraint to a detailed mathematical functional specification. Requirements may serve a dual function:

- The basis for a bid for a contract, thus must be open to interpretation.
- The basis for the contract itself, therefore must be defined in detail.

Both these statements may be called requirements.

## Requirements Engineering

Requirements engineering is the process of finding out, analyzing, documenting, and checking services and constraints. It involves establishing the services that the customer requires from a system and the constraints under which it operates and is developed. The requirements themselves are the descriptions of the system services and constraints generated during the requirements engineering process.

### Requirements Abstraction (Davis)

When letting a contract for a large software development project, a company must define its needs in an abstract way to allow multiple contractors to bid, offering different solutions. After a contract is awarded, the contractor writes a more detailed system definition for the client to understand and validate, and both documents may be called the requirements document for the system.

## Types of Requirement

- **User Requirements**: Statements in natural language plus diagrams of the services the system provides and its operational constraints, written for customers.
  
- **System Requirements**: A structured document outlining detailed descriptions of the system's functions, services, and operational constraints. It defines what should be implemented and may be part of a contract between the client and contractor.

## Definitions and Specifications

- **User Requirement Definition**: The software must provide the means of representing and accessing external files created by other tools.

- **System Requirement Specification**:
  - The user should be provided with facilities to define the type of external files.
  - Each external file type may have an associated tool that may be applied to the file.
  - Each external file type may be represented as a specific icon on the user's display.
  - Facilities should be provided for the icon representing an external file type to be defined by the user.
  - When a user selects an icon representing an external file, the effect of that selection is to apply the tool associated with the type of the external file to the file represented by the selected icon.

## Requirements Readers

### Functional and Non-functional Requirements

- **Functional Requirements**: Statements of services the system should provide, specifying how the system should react to particular inputs and behave in specific situations.

- **Non-functional Requirements**: Constraints on the services or functions offered by the system, including timing constraints, development process constraints, standards, etc.

- **Domain Requirements**: Requirements from the application domain of the system reflecting characteristics of that domain.

