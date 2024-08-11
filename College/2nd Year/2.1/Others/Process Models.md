# PROCESS MODELS

Prescriptive process models define a set of activities, actions, tasks, milestones, and work products required for engineering high-quality software. Although not perfect, these models offer a useful roadmap for software engineering work. A prescriptive process model populates a process framework with explicit task sets for software engineering actions.

## THE WATERFALL MODEL

The waterfall model, also known as the classic life cycle, proposes a systematic sequential approach to software development. It begins with customer specification of requirements and progresses through planning, modeling, construction, and deployment.
![[Pasted image 20231111190934.png]]
**Context:**
- Used when requirements are reasonably well understood.

**Advantage:**
- Useful in situations where requirements are fixed, and work proceeds to completion in a linear manner.

**Challenges:**
1. **Sequential Flow:** Real projects rarely follow the sequential flow proposed by the model. While it can accommodate iteration, it does so indirectly, leading to potential confusion as changes occur.
   
2. **Requirement Understanding:** Difficulty in explicitly stating all requirements. The model struggles to accommodate the natural uncertainty present at the beginning of many projects.

3. **Customer Patience:** The customer needs patience as a working version of the software is not available until late in the project time-span. If a major error is undetected, it can be disastrous until the program is reviewed.

The waterfall model's rigidity in handling changes and the need for explicit requirements make it less suitable for dynamic and uncertain project environments. While it provides a clear structure, its applicability is limited in scenarios where flexibility and adaptability are crucial.

# Evolutionary Process Model

Evolutionary process models, characterized by iterative development, aim to produce increasingly more complete versions of software with each iteration. Two notable evolutionary models are Prototyping and the Spiral Model.

- Software evolves over time.
- Business and product requirements often change during development.
- Straight-line paths to an end product are unrealistic.
- Evolutionary models are iterative and applicable to modern applications.

## Types of Evolutionary Models

1. **Prototyping**
2. **Spiral Model**
3. **Concurrent Development Model**

## THE SPIRAL MODEL

The Spiral Model, proposed by Boehm, combines the iterative nature of prototyping with the systematic aspects of the waterfall model. It facilitates the development of software in evolutionary releases through multiple iterations. Each iteration results in increasingly more complete versions of the software.
![[Pasted image 20231111191126.png]]
**Key Features:**
- **Iterative Evolution:** Early iterations may involve a paper model or prototype, while later iterations produce more sophisticated software versions.
- **Anchor Points:** Milestones marked along the spiral, representing work products and conditions attained for each evolutionary pass.
- **Adjustable Planning:** Adjustments to project plans, costs, and schedules are made based on customer feedback after each iteration.

**Context:**
- Applicable throughout the entire life cycle of an application, from concept development to maintenance.

**Advantages:**
- Potential for rapid development of increasingly complete software versions.
- Realistic approach for large-scale systems.
- Utilizes prototyping for risk reduction at any project stage.

**Drawbacks:**
- Difficult to convince customers of controllability.
- Requires significant risk assessment expertise.
- Dependence on expertise for risk management; major risks not uncovered may lead to problems.

# Agile Process Model

- The meaning of Agile is swift or versatile. "Agile process model" refers to a software development approach based on iterative development.
- Agile methods break tasks into smaller iterations, or parts do not directly involve long-term planning.
- The project scope and requirements are laid down at the beginning of the development process.
- Plans regarding the number of iterations, the duration, and the scope of each iteration are clearly defined in advance.
- Each iteration is considered as a short time "frame" in the Agile process model, which typically lasts from one to four weeks.
- The division of the entire project into smaller parts helps to minimize the project risk and to reduce the overall project delivery time requirements.
- Each iteration involves a team working through a full software development life cycle including planning, requirements analysis, design, coding, and testing before a working product is demonstrated to the client.
![[Pasted image 20231109190203.png]]
## Phases of Agile Model:

1. **Requirements Gathering**
2. **Design the Requirements**
3. **Construction/Iteration**
4. **Testing/Quality Assurance**
5. **Deployment**
6. **Feedback**

### Requirements Gathering:

In this phase, you must define the requirements. You should explain business opportunities and plan the time and effort needed to build the project. Based on this information, you can evaluate technical and economic feasibility.

### Design the Requirements:

When you have identified the project, work with stakeholders to define requirements. You can use the user flow diagram or the high-level UML diagram to show the work of new features and show how it will apply to your existing system.

### Construction/Iteration:

When the team defines the requirements, the work begins. Designers and developers start working on their project, which aims to deploy a working product. The product will undergo various stages of improvement, so it includes simple, minimal functionality.

### Testing:

In this phase, the Quality Assurance team examines the product's performance and looks for bugs.

### Deployment:

In this phase, the team issues a product for the user's work environment.

### Feedback:

After releasing the product, the last step is feedback. In this, the team receives feedback about the product and works through the feedback.

## Advantages (Pros) of Agile Method:

- Frequent Delivery
- Face-to-Face Communication with clients.
- Efficient design and fulfills the business requirement.
- Anytime changes are acceptable.
- It reduces total development time.

## Disadvantages (Cons) of Agile Model:

- Due to the shortage of formal documents, it creates confusion and crucial decisions taken throughout various phases can be misinterpreted at any time by different team members.
- Due to the lack of proper documentation, once the project completes and the developers allotted to another project, maintenance of the finished project can become a difficulty.