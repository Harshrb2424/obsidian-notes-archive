# System Requirements

System requirements provide more detailed specifications of system functions, services, and constraints than user requirements. They serve as the basis for designing the system and may be incorporated into the system contract. These requirements can be defined or illustrated using system models.

## Relationship Between Requirements and Design

In principle, requirements state what the system should do, while design describes how it achieves this. However, in practice, requirements and design are inseparable. A system architecture may be designed to structure the requirements, and specific designs may be influenced by domain requirements.

## Challenges with Natural Language (NL) Specification

1. **Ambiguity**: NL is naturally ambiguous, making it challenging for both readers and writers to interpret the same words in the same way.
2. **Over-flexibility**: The same concept may be expressed in various ways in the specification.
3. **Lack of Modularization**: NL structures are often inadequate for structuring system requirements.

## Alternatives to NL Specification

1. **Structured Natural Language Specifications**: This approach relies on defining standard forms or templates to express requirements.

2. **Design Description Languages**: Using a language resembling a programming language with more abstract features to define an operational model of the system.

3. **Graphical Notations**: Utilizing graphical languages, supplemented by text annotations, to define functional requirements. Examples include use-case descriptions and sequence diagrams.

4. **Mathematical Specifications**: Notations based on mathematical concepts, such as finite-state machines or sets, providing unambiguous specifications. However, customers may find formal specifications challenging to understand.

### 3.1) Structured Language Specifications

- **Freedom Limitation**: Writers are limited by predefined templates.
- **Standardization**: Requirements are written uniformly.

### Form-based Specifications

- Definition of the function or entity.
- Description of inputs and their sources.
- Description of outputs and their destinations.
- Indication of other required entities.
- Pre and post-conditions.
- Side effects.

### Tabular Specifications

- Useful for defining alternative courses of action.

### Graphical Models

- Useful for showing state changes or describing a sequence of actions.
- Examples include sequence diagrams.
![[Pasted image 20231116200404.png]]
## System Requirement Specification Using a Standard Form

- **Function**: Description of the function or entity.
- **Inputs**: Description of inputs and their sources.
- **Outputs**: Description of outputs and their destinations.
- **Action**: Description of the action to be taken.
- **Requires**: Indication of other entities used.
- **Pre-condition**: Setting out what must be true before the function is called.
- **Post-condition**: Specifying what is true after the function is called.
- **Side-effects**: Description of the side effects of the operation.