# Functional Requirements

Functional requirements describe the functionality or system services, depending on the type of software, expected users, and the system's type of use. While functional user requirements may be high-level statements of what the system should do, functional system requirements should provide a detailed description of the system services.

## LIBSYS System Functional Requirements

The LIBSYS system, a library system providing a single interface to databases of articles in different libraries, has the following functional requirements:

1. The user shall be able to search either all of the initial set of databases or select a subset from it.
2. The system shall provide appropriate viewers for the user to read documents in the document store.
3. Every order shall be allocated a unique identifier (ORDER_ID), which the user shall be able to copy to the account's permanent storage area.

### Requirements Imprecision

Problems arise when requirements are not precisely stated. Ambiguous requirements may be interpreted differently by developers and users. For example, the term 'appropriate viewers' can be interpreted differently:
- User intention: Special purpose viewer for each different document type.
- Developer interpretation: Provide a text viewer that shows the contents of the document.

### Requirements Completeness and Consistency

In principle, requirements should be both complete and consistent:
- **Complete**: They should include descriptions of all required facilities.
- **Consistent**: There should be no conflicts or contradictions in the descriptions of the system facilities. However, in practice, producing a complete and consistent requirements document is challenging.

# Non-functional Requirements

Non-functional requirements define system properties and constraints such as reliability, response time, and storage requirements. These requirements may be more critical than functional requirements, as the system becomes useless if they are not met.

## Non-functional Requirement Types

1. **Product Requirements**: Specifications that the delivered product must behave in a particular way (e.g., execution speed, reliability). Example: The user interface for LIBSYS shall be implemented as simple HTML without frames or Java applets.

2. **Organisational Requirements**: Consequences of organizational policies and procedures (e.g., process standards, implementation requirements). Example: The system development process and deliverable documents shall conform to the process and deliverables defined in XYZCo-SP-STAN-95.

3. **External Requirements**: Arise from factors external to the system and its development process (e.g., interoperability requirements, legislative requirements). Example: The system shall not disclose any personal information about customers apart from their name and reference number to the operators of the system.

## Goals and Requirements

Non-functional requirements, especially goals, may be challenging to state precisely and verify. Goals express general user intentions, while verifiable non-functional requirements provide measurable statements for testing.

- **Goal**: The system should be easy to use by experienced controllers and should be organized in such a way that user errors are minimized.

- **Verifiable Non-functional Requirement**: Experienced controllers shall be able to use all system functions after a total of two hours of training. After training, the average number of errors made by experienced users shall not exceed two per day.

## Requirements Measures

| Property | Measure |
| --- | --- |
| Speed | Processed transactions/second, User/Event response time, Screen refresh time |
| Size | M Bytes, Number of ROM chips |
| Ease of use | Training time, Number of help frames |
| Reliability | Mean time to failure, Probability of unavailability, Rate of failure occurrence, Availability |
| Robustness | Time to restart after failure, Percentage of events causing failure, Probability of data corruption on failure |
| Portability | Percentage of target-dependent statements, Number of target systems |

## Requirements Interaction

Conflicts between different non-functional requirements are common in complex systems, as illustrated by the example of a spacecraft system trying to minimize weight and power consumption simultaneously. Resolving such conflicts is crucial for successful system development.

A common challenge with non-functional requirements is their difficulty to verify, often stated as vague goals. Users may express these requirements as general goals, leaving room for interpretation and potential disputes after system delivery.