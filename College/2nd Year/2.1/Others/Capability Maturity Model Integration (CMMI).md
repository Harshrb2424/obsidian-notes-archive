# THE CAPABILITY MATURITY MODEL INTEGRATION (CMMI)

The CMMI represents a process meta-model in two different ways: As a continuous model and as a staged model. Each process area is formally assessed against specific goals and practices, and is rated according to the following capability levels.

## Capability Levels:

### Level 0: Incomplete
- The process area is either not performed or does not achieve all goals and objectives defined by CMMI for level 1 capability.

### Level 1: Performed
- All specific goals of the process area have been satisfied.
- Work tasks required to produce defined work products are being conducted.

### Level 2: Managed
- All level 1 criteria have been satisfied.
- Additionally, all work associated with the process area conforms to an organizationally defined policy.
- All people doing the work have access to adequate resources to get the job done.
- Stakeholders are actively involved in the process area as required.
- All work tasks and work products are "monitored, controlled, and reviewed."

### Level 3: Defined
- All level 2 criteria have been achieved.
- The process is "tailored from the organization's set of standard processes according to the organization's tailoring guidelines."
- Contributes work products, measures, and other process-improvement information to the organizational process assets.

### Level 4: Quantitatively Managed
- All level 3 criteria have been achieved.
- The process area is controlled and improved using measurement and quantitative assessment.
- Quantitative objectives for quality and process performance are established and used as criteria in managing the process.

### Level 5: Optimized
- All level 4 criteria have been achieved.
- Additionally, the process area is adapted and optimized using quantitative means to meet changing customer needs and to continually improve the efficacy of the process area under consideration.

**Note:** Each level represents a maturity stage, and achieving higher levels indicates a more mature and optimized organizational process.


The CMMI defines each process area in terms of "specific goals" and the "specific practices" required to achieve these goals. Specific practices refine a goal into a set of process-related activities.

## Project Planning Process Area

### Specific Goals (SG) and Associated Specific Practices (SP):

- **SG 1 Establish estimates:**
  - SP 1.1 Estimate the scope of the project.
  - SP 1.2 Establish estimates of work product and task attributes.
  - SP 1.3 Define project life cycle.
  - SP 1.4 Determine estimates of effort and cost.

- **SG 2 Develop a Project Plan:**
  - SP 2.1 Establish the budget and schedule.
  - SP 2.2 Identify project risks.
  - SP 2.3 Plan for data management.
  - SP 2.4 Plan for needed knowledge and skills.
  - SP 2.5 Plan stakeholder involvement.
  - SP 2.6 Establish the project plan.

- **SG 3 Obtain commitment to the plan:**
  - SP 3.1 Review plans that affect the project.
  - SP 3.2 Reconcile work and resource levels.
  - SP 3.3 Obtain plan commitment.

### Generic Goals (GG) and Practices (GP):

- **GG 1 Achieve specific goals:**
  - GP 1.1 Perform base practices.

- **GG 2 Institutionalize a managed process:**
  - GP 2.1 Establish an organizational policy.
  - GP 2.2 Plan the process.
  - GP 2.3 Provide resources.
  - GP 2.4 Assign responsibility.
  - GP 2.5 Train people.
  - GP 2.6 Manage configurations.
  - GP 2.7 Identify and involve relevant stakeholders.
  - GP 2.8 Monitor and control the process.
  - GP 2.9 Objectively evaluate adherence.
  - GP 2.10 Review status with higher-level management.

- **GG 3 Institutionalize a defined process:**
  - GP 3.1 Establish a defined process.
  - GP 3.2 Collect improvement information.

- **GG 4 Institutionalize a quantitatively managed process:**
  - GP 4.1 Establish quantitative objectives for the process.
  - GP 4.2 Stabilize sub-process performance.

- **GG 5 Institutionalize and optimizing process:**
  - GP 5.1 Ensure continuous process improvement.
  - GP 5.2 Correct root causes of problems.

**Note:** Achieving these generic goals is essential for progressing through the capability levels.

# PROCESS PATTERNS

The software process can be defined as a collection of patterns that define a set of activities, actions, work tasks, work products, and/or related behaviors required to develop computer software.

## Process Pattern Components:

1. **Pattern Name:**
   - Given a meaningful name describing its function within the software process.

2. **Intent:**
   - Briefly describes the objective of the pattern.

3. **Type:**
   - Specifies the pattern type (Task, Stage, Phase).

4. **Initial Context:**
   - Describes conditions under which the pattern applies.

5. **Problem:**
   - Describes the problem to be solved by the pattern.

6. **Solution:**
   - Describes the implementation of the pattern and how it modifies the initial state of the process.

7. **Resulting Context:**
   - Describes the conditions that result once the pattern has been successfully implemented.

8. **Known Uses:**
   - Indicates specific instances in which the pattern is applicable.

Process patterns provide an effective mechanism for describing any software process. They enable a software engineering organization to develop a hierarchical process description starting at a high level of abstraction. Once developed, patterns can be reused for defining process variants, allowing teams to use them as building blocks for customized process models.

# PROCESS ASSESSMENT

The existence of a software process is no guarantee that software will be delivered on time, meet customer needs, or exhibit the technical characteristics leading to long-term quality. Additionally, assessing the process itself is essential to ensure it meets basic criteria for successful software engineering.

## Software Capability

- **Motivation:** Identifies capabilities and risks.
- **Lead:** Software Lead.

Several approaches to software process assessment have been proposed:

1. **Standards CMMI Assessment Method for Process Improvement (SCAMPI):**
   - Five-step process assessment model (Initiating, Diagnosing, Establishing, Acting, Learning).
   - Uses SEI CMMI as the basis for assessment.

2. **CMM Based Appraisal for Internal Process Improvement (CBA IPI):**
   - Diagnostic technique for assessing the relative maturity of a software organization.
   - Uses SEI CMM as the basis for assessment.

3. **SPICE (ISO/IEC15504) Standard:**
   - Defines requirements for software process assessments.
   - Aims to assist organizations in objectively evaluating the efficacy of any defined software process.

4. **ISO 9001:2000 for Software:**
   - Generic standard applicable to organizations seeking to improve overall product, system, or service quality.
   - Directly applicable to software organizations and companies.

## PERSONAL AND TEAM PROCESS MODELS

The best software process is one that is close to the people doing the work. Each software engineer or team would create a process that fits their needs while meeting broader organizational needs.

### Personal Software Process (PSP)

PSP emphasizes personal measurement of work product and resultant quality. The process model includes:

1. **Planning:**
   - Isolates requirements, develops size and resource estimates, and makes defect estimates.
   - Identifies development tasks and creates a project schedule.

2. **High-Level Design:**
   - Develops external specifications for components, creates component designs.
   - Prototypes built when uncertainty exists.

3. **High-Level Design Review:**
   - Applies formal verification methods to uncover errors in the design.
   - Maintains metrics for all important tasks and work results.

4. **Development:**
   - Refines and reviews component-level design, generates, reviews, compiles, and tests code.
   - Maintains metrics for all important tasks and work results.

5. **Postmortem:**
   - Determines the effectiveness of the process using collected measures and metrics.
   - Provides guidance for modifying the process to improve effectiveness.

PSP stresses early error identification and a metrics-based approach to software engineering.

### Team Software Process (TSP)

TSP aims to build self-directed project teams that organize themselves to produce high-quality software. Objectives include:

- Building self-directed teams that plan and track their work, establish goals, and own their processes and plans.
- Coaching and motivating teams to sustain peak performance.
- Accelerating software process improvement, making CMM level 5 behavior normal and expected.

TSP defines the following framework activities: launch, high-level design, implementation, integration and test, and postmortem.

A self-directed team in TSP:

- Defines roles and responsibilities for each team member.
- Tracks quantitative project data.
- Identifies a team process appropriate for the project.
- Develops a strategy for implementing the process.
- Defines local standards applicable to the team's software engineering work.
- Continually assesses and reacts to risk.
- Tracks, manages, and reports project status.

TSP utilizes scripts, forms, and standards to guide team members. Scripts define specific process activities and detailed work functions.

Each project is "launched" using a sequence of tasks, including reviewing project objectives, establishing team roles, defining the development process, making a quality plan, and setting quality targets.

This emphasis on both personal and team-oriented processes aims to improve software development outcomes.

