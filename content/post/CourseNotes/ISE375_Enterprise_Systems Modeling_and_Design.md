---
title: ISE375 Enterprise Systems Modeling and Design
date: 2023-04-21
updated: 2023-02-15
tags: [2022, Course Notes, Computer Science, Industrial and Systems Engineering]
categories: "Course Notes"
keywords:
summary: The overview of course ISE375 Enterprise Systems Modeling and Design
top_img: 
comments: true
cover:
toc:
toc_number:
toc_style_simple:
copyright:
copyright_author:
copyright_author_href:
copyright_url:
copyright_info:
mathjax: true
katex:
aplayer:
highlight_shrink:
aside:
abcjs:
draft: true
---


<span style = '/img/CN_ISE375/font-family: Times New Roman'>

> 📢 Disclaimer
> Copyright © [The Hong Kong Polytechnic University, Faculty of Engineering, Department of Industrial & Systems Engineering](https://www.polyu.edu.hk/ise/)
> The lecture notes is for reference only, permission is hereby granted, free of charge, to any person obtaining a copy of this documentation file, to deal in the Page without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Page is furnished to do so.
> The authors or copyright holders are not be liable for any claim, damages or other liabillty, whether in an action of contract, tort or otherwise, arising from, out of or in connection with or the use or other dealings in the Page.

**Principles of Enterprise Modeling:**
Fundamentals of enterprise systems
Common types modeling skill in enterprise systems nowadays such as Entity modeling; Process modeling, Object modeling 
Closing down and maintaining the project
**Techniques:**
Diagramming how the system will function 
Conducting interview of current and future users for the system 
Planning and managing the functions in a system

---

# Lecture 1 INTRODUCTION 

## 1.1 The Systems Development Life Cycle (SDLC)


<center><img src = '/img/CN_ISE375/L1SDLC.png' width = 350></center>

### Phase 1: System planning and selection


**1st task: Identification of the needs for a new or enhanced system**
The needs are normally:
Requests to deal with the problems in current procedures
The desire to perform additional tasks
Realization the breakthrough of an existing opportunity by IT


**2nd Task: Prioritize, translate the needs and allocate the resources**
After 1st task, we have known the needs and the reasons for a new system. 
Prioritize the needs
Translate the need into the written plans for the system, ex. Schedule for developing the system, the derivable of the system 
e.g., user may have some comments and needs ,user-friendly, low cost…the descriptions are blurry and what you need do is to make it into detailed
Allocate the resources


**3rd Task: Determine the proposed system’s scope and its value to the business**
After 2nd task, we have briefly known the general scope of the plan for the new system
Investigate and determine the proposed system scope
Generate the specific plans for the team to follow, including Time estimation, Task identification, Work, Breakdown structure, Project staffing, Standards, and Risk management 


**Consider the problems relating to the systems (# how to achieve)**
The technical feasibility (Can we build it?) 
The economic feasibility (Will it provide business value?)
The organizational feasibility (If we build it, can it be used?) 


### Phase 2: System analysis

During this phase, the analyst thoroughly studies the organization’s current procedures and the information systems used to perform tasks such as general ledger, shipping, order entry, machine scheduling, and payroll.

**1st Task – Determine the user requirements**
Work with current and potential users to determine what the users want from the proposed system
Study of CURRENT systems, manual and computer system to find out the wanted gap
Eliminate the redundancy of the new system


**2nd task – Generate alternatives**
Compare and evaluate the advantages and disadvantages between the alternatives include: Cost, labour, technical level
3rd task– Output of the analysis
Summarize the previous steps in a proposal deliverable that is presented to the project sponsor and other key individuals who decide whether the project should continue to move forward.
Analysis and finally recommend the solution among all the alternatives with all the teammates




### Phase 3: System design

After confirming the alternative, analysts convert the description of the alternatives into logical and then physical system specification, from input to output. It includes:
**Logical design: # use techniques to draw it out** 
Your design can be implemented on any software and hardware (means you can design the idea by any software such as solidworks, cad etc)
Concentrate on the business aspect – how the system will benefit and impact the functional unit of organization 


**Physical design:**
Turn the logical design into physical objects. E.g., convert the diagram into a real object
Design Strategy: This clarifies whether the system will be developed by the company or outside the company.
Architecture Design: This describes the hardware, software, and network infrastructure that will be used.
Database and File Specifications: These documents define what and where the data will be stored.
Program Design: Defines what programs need to be written and what they will do.



### Phase 4: System implementation and operation
Turn system specifications into a working system in reality

Coding: Programmers write the programs that make up the system
Testing: Programmers and analysts test individual programs and entire system in order to find the bugs and correct them
Installation: Install the application software on existing or new hardware
Training and ongoing user assistance: Users could use the systems and ask for continuous supports

New release version and associated update of system: users may find problems with the system, programmer makes changes and updates the functions of the system



# Lecutre 2 PROJECT MANAGEMENT

**Project initiation**
This request will be reviewed by the “system priority board” (As the limitation of the resource in the company), aiming to evaluate the requests in the  relation to the business problems and the opportunity solve or create. 
The broad selects the requests that best match with overall needs. Approved
Selection criteria: Take advantages to solve the business problem, take advantages of  providing innovation service to improve the customer experience.
Sometime projects are not initiated by rational reasons (for example? Why)


**Project planning**
1. Describing project scope, alternatives, and feasibility
Ask yourself questions (scope):
What problem or opportunity does the project address?
What are the quantifiable results to be achieved?
What needs to be done?
How will the success be measured?
The questions above enable to guild you to observe how “big” is the project


2. Dividing the project into manageable tasks
Redefine the work tasks into “work breakdown structure”  -  sequence, priority, parallel or not
Use Gantt chart


3. Estimating resources and creating resource plans
COCOMO (COnstructive COst Model)
Resources include: people, skillful people, , technological capability
Resource allocation (to minimize the cost and best uses of resources for the plan)

4. Developing a preliminary schedule
5. Create the starting time based on the estimated resource and the work breakdown (previous tasks)
Gannt Chart
Network diagram

$$
E T=\frac{o+4 r+p}{6}
$$
where
$E T=$ expected time for the completion for an activity
$o=$ optimistic completion time for an activity
$r=$ realistic completion time for an activity
$p=$ pessimistic completion time for an activity



6. Developing a communication plan
To outline the communication procedures among management, project team members, when and how written and oral reports will be provided, how teams coordinate. 


7. Determining project standards and procedures
How the deliverable be produced? So we need a standard and procedures
How the standard of SDLC be modified?
What documentation styles?



8. Identifying and assessing risks
- The goal for this task is to estimate the project risk and plan for the consequence of those risks
- Risks: adopt of new technology, users resistance to change, available of critical resources, competitive reactions


9. Creating a preliminary budget
- Create a preliminary budget that outlines the planned expense and revenues associated with your project. 
- The project justifications will demonstrate that the benefits are worth these costs. 
-  Better to show what exactly revenue and cost (cash flow analysis)


10. Developing a project scope statement
The statement clearly states what the project will deliver, what things can be achieved after the project. (1-2 sentence to conclude)
Project size, duration, outcomes, number of people involved

11. Setting a baseline project plan
- A baseline in project management is a clearly defined starting point for your project plan. It is a fixed reference point to measure and compare your project’s progress against. 
- Evaluate and updated the project plan after a period


**Project execution**
1. Executing the baseline project plan
Initiation the execution of project activities, acquire and assign resources, orient and train new team members, keep the project on schedule and ensure the quality of the project deliverables


2. Managing changes to the baseline project
- Any change  must be approved ( involves many steps) and must be marked in the baseline plan, chat and workbook
1. Formal request, including the reason of change and all the possible impacts from the change (cost or any resource)
2. The formal request is approved by upper management (the project steering committee evaluates the requests)
The reasons of change:
1. Delay of completion date for an activity
2. The identification of new activity
3. An unforeseen change in personal due to sickness and resignation. 



3. Maintaining the project workbook
Communicating the project status
Project managers should be responsible for keeping all team member notice about the project status.
- Especially two types of results
1. Work results, outcomes of the various tasks and activities that are given complete the project
2. The project plan, budgets, schedule, project charter and risk plan.


**Closing down the project**
After execution of the project, the project comes to the end
Nature termination: occurs when all the requirement and objectives of the project have been met – success
Unnatured termination: Occur when the project is stopped before completion (reason? Money? Technical capability?)
no matter nature or unnatural termination – “close down the project” must be conducted
1. Closing down the project
Team member: provide appraisal for personal file and salary determination, career advice, writing referral letter, send thank you letter 
Related parties: Notify them that the project has been finished 
Documentation: Finalize all the documents relating to the project, organize them and file them

2. Post-project review
To determine the strengths and weaknesses of the processes of the project.
To improve the process for next project

3. Closing related contracts
To ensure all the contractual items of the project have been met. 
Gain agreement from related parties


---

# Lecture 3 MODELING IN ENTERPRISE SYSTEMS: PROCESS MODELING AND LOGIC MODELING

Process Modeling
Graphically representing the processes that capture and distribute data between a system and its environment

## 3.1 DFD (Data Flow Diagram)

> Data flow – data that are in motion and moving as a unit from one place in a system to another.
Data Store – data at rest. A data store represents one of many different physical locations for data including a file folder, once or more computer-based file(s). A data store might contain data about customers , students, customer orders, or supplier invoices
Process – the work or actions performed on data so that they are transformed, stored and distributed.
Source/ Sink – is the origin and/or destination of data. Source/sinks are sometimes referred to as external entities because they are outside the system. 
Arrow: each arrow should be named as a meaningful name to represent its function, such as payment, receipt etc.
Rectangle with the right vertical line missing (Data store) : includes the number of the data files (D1, D2 stc..) and a meaning name such as student file, customer master stc.
Rectangle with round corner: process such as record payment, make bank deposit. Need to write both the number of the process and the name which indicate the process
Rectangle square (source/sinks): external agents such as customers, teller, inventory control system (we don’t investigate how the data processes in the source/sink)

### 3.1.1 DFD Mechanics
> Arrow: each arrow should be named as a meaningful name to represent its function, such as payment, receipt etc.
Rectangle with the right vertical line missing (Data store) : includes the number of the data files (D1, D2 stc..) and a meaning name such as student file, customer master stc.
Rectangle with round corner: process such as record payment, make bank deposit. Need to write both the number of the process and the name which indicate the process
Rectangle square (source/sinks): external agents such as customers, teller, inventory control system (we don’t investigate how the data processes in the source/sink)


As sources and sinks are outside the system, many of their characteristics are not studied. In particular, we do not consider the following:
interactions that occur between sources and sinks
What a source or sink does with information or how it operates (i.e. a source or sink is a “black box”)
How to control or resign a source or sink 
How to provide sources and sinks direct access to stored data 


<center><img src = '/img/CN_ISE375/DFD1.png' width = 350></center>

**[Example]**

Four separate processes are divided from “0” process
Capturing data from different sources (1.0)
Maintaining data stores (2.0 and 3.0)
Producing and distributing data to different sinks (4.0)
High-level descriptions of data transformation operations (1.0)

The results are four streams or flows of data: 
The food order is transmitted to the kitchen
The customer order is transformed into a list of goods sold
The customer order is transformed into inventory data
The process generates a receipt for the customer




<center><img src = '/img/CN_ISE375/DFD2.png' width = 350></center>

## 3.2 Decompositions of DFD

Level 1 diagram
Labeled as a subprocess of Process 1.0: Process 1.1, Process 1.2, and so on
We could decide to decompose Processes 2.0, 3.0, or 4.0 in a similar manner
A level-n diagram is a DFD that is generated from n decompositions from a level-0 diagram.

<center><img src = '/img/CN_ISE375/DFD3.png' width = 350></center>


Level 0 shows three outputs: the customer receipt, the food order intended for the kitchen, and management reports.
The data flow appears at previous level = that of the current level -  balancing DFD
No new inputs or outputs have been added. 


<center><img src = '/img/CN_ISE375/DFD4.png' width = 350></center>

**[Example]**

> 1. Determine data store, process and source/sink for the above situation
> 2. Draw a level-0 diagram for the above situations based on Step 1 information

Source: patient (request)
Sink: (record) patient

Process:
1. collect basic demographic info. (new info)
2. verify health info. (vaildated info)
3. save info into the patient registry  (status)
4. check
5. ensure if a patient got a record
6. if no, need record (new record)
7. collect medical info. (weight…)
8. place it into system  (all docs) 
9. arrange the patient (prescribes medication or treatment)
10. send patient to checkout (payment and record)
11. collect payment (perscriptions/ record)
Data Source/Store: 
1. (client info) Patient registry 
2. (info record) Record system 


<center><img src = '/img/CN_ISE375/DFD.png' width = 350></center>




## 3.3 Logic Modeling

Logic modeling involves representing the internal structures and functionality of the processes on data-flow diagrams. 
Tell the structure and functionality of system’s processes clearly
Decision tables is made in a tabular format a set of conditions 

<center><img src = '/img/CN_ISE375/LogicalModeling.png' width = 350></center>
Name the conditions and the values each condition can assume. Determine all of the conditions that are relevant to your problem, and then determine all of the values each condition can take. For some conditions, the values will be simply “yes” or “no”. For others, the conditions may have more values (like the example). 
Name all possible actions that can occur. The purpose of creating decision tables is to determine the proper course of action given a particular set of conditions.
List all possible rules. Every possible combination of conditions must be represented. To determine the number of rules, multiply the number of values for each condition by the number of values for every other condition. In the example, we have two conditions, one with two values and one with three, so we need 2 × 3, or 6, rules. If we added a third condition with three values, we would need 2 × 3 × 3, or 18, rules.
Define the actions for each rule. Now that all possible rules have been identified, provide an action for each rule. 
Simplify the decision table. Remove the rules with indifferent conditions or impossible rule

--

# Lecture 4 OBJECT-ORIENTED MODELLING (OOM)

The techniques which are incorporated into a standard object-oriented language are called the Unified Modeling Language (UML)
UML include:
Use cases, which represent the functional requirements or the “what” of the system

1. Use-case modeling is done in the early stages of system development (during the analysis phase) to help developers understand the functional requirements of the system, which would show complete functionality.
2. A use-case model consists of actors and use cases. 
3. An actor is an external entity that interacts with the system. It is someone or something that exchanges information with the system. 
4. A use case represents a sequence of related actions initiated by an actor; it is a specific way of using the system. 
5. The actor’s name should indicate that role.

An university registration system has a use case for class registration and another for student billing. 

**[Example]**

<center><img src = '/img/CN_ISE375/OOM.png' width = 350></center>

Actors
Student, Registration clerk, Instructor, and Bursar’s office
Using a stick figure with its name below
Located outside the box
interact with the system(shown by the lines touching the actors)
Cases
Class registration, Registration for special class, Prereq courses not completed, and Student billing
shown as ellipses with their names inside
use cases are performed by the actors outside the system


An extends relationship - A use case may participate in relationships with other use cases
labeled with the “<<extends>>” 
The” Registration for special class use case” extends the “Class registration use case” by capturing the additional actions


Systems development life cycle consists of a continuously developing object within the system
Object-oriented modeling (OOM) is typically done via use of the most important objects. 
OMM is the construction of objects using a collection of objects that contain stored values of the instance variables found within an object. 
Unlike models that are record-oriented, object-oriented values in OOM are solely objects.




---

# Lecture 5 CONCEPTUAL DATA MODELLING

## 5.1 ER diagram
> 1. Identify the entities in in a data model
> 2. To fill in the elements inside the entities (PK, Attribute, etc.)
> 3. To complete the E-R diagram, we must determine necessary relationships among these entities as well as attributes for each entity


Three main constructs: data entities, relationships, and their associated attributes
Entity-relationship (E-R) diagram is:
- a logical, and graphical representation of the data for an organization or business area. 
- The E-R diagram is a model of entities in the business environment, the relationships or associations among those entities, and the attributes or properties of both the entities and their relationships. 
- A rectangle is used to represent an entity, and lines are used to represent the relationship between two or more entities. 
<center><img src = '/img/CN_ISE375/ER2.png' width = 350></center>

## 5.2 Entity

An `entity` is a person, place, object, event, or concept in the user environment about which the organization wishes to maintain data. An entity has its own identity, which distinguishes it from every other entity

**[Example]**
Person: EMPLOYEE, STUDENT, PATIENT 
Place: STATE, REGION, COUNTRY, BRANCH 
Object: MACHINE, BUILDING, AUTOMOBILE, PRODUCT 
Event: SALE, REGISTRATION, RENEWAL 
Concept: ACCOUNT, COURSE, WORK CENTER


Distinction between `entity types` and `entity instances`
Entity type is a collection of entities that share common properties or characteristics
Each entity type in an E-R model is given a name – singular, simple noun and capital letters
The name is placed inside a rectangle representing the entity type

**[Example]**
Most organizations have one `EMPLOYEE` entity type, but hundreds of instances of this entity type `(John, Peter etc….)` may be stored in the database.


## 5.3 Attributes
Attribute is a named property or characteristic of an entity that is of interest to the organization.
Entity type has a set of attributes associated with it. 

Use an initial capital letter followed by lowercase letters in naming an attribute
In E-R diagrams, we represent an attribute by placing its name inside the rectangle that represents the associated entity.

Some typical entity types and associated attributes:
STUDENT: Student_ID, Student_Name, Address, Phone_Number, Major 
AUTOMOBILE: Vehicle_ID, Color, Weight, Horsepower 
EMPLOYEE: Employee_ID, Employee_Name, Address, Skill

## 5.4 Candidate Keys and Identifiers
A candidate key is an attribute (or combination of attributes) that uniquely identifies each instance of an entity type
Find the attribute which uniquely represents the entity instance – candidate keys
E.g. A candidate key for a STUDENT entity type might be Student_ID
E.g. The entity type GAME for Olympic. The attribute “Team_Name” is clearly not a candidate key, because each team plays several games in Olympic.

Some entities have more than one candidate key. E.g. EMPLOYEE: Employee_ID, Employee_Name and Address 
In this case, the designer must choose one of the candidate keys as the identifier. 
An identifier is a candidate key that has been selected to be used as the unique characteristic for an entity type


The rule of selection identifiers:
Choose a candidate key that will not change its value over the life. E.g.: Employee_ Name and Address is not a good identifier  because the values of Employee_Name and Address could easily change during an employee’s term of employment
Choose a candidate key such that for each instance of the entity, the attribute is guaranteed to have valid values and not be null. E.g.: EMPLOYEE: Computer Skill (can have no skill for the employee sometime)
The identifier is underlined on an E-R diagram for each entity

## 5.5 Multivalued attributes

Multivalued attribute means there are more than one value for each entity instance.

Skill is one of the attributes of EMPLOYEE, which employees can have more than one Skill, then it is a multivalued attribute.
Use curly brackets around the name of the multivalued attribute


## 5.6 Relationships
A relationship is an association between entity types that are of interest to the organization.
An association usually means that an event has occurred or that some natural linkages exist between entity instances
Relationships are labeled with verb phrases
E.g.: example, a training department in a company is interested in tracking which training courses each of its employees has completed. 
The symbol means many-to-many relationship: Each employee may complete more than one course, and each course may be completed by more than one employee

### 5.6.1 Degree of relationship
Completes:  degree two because it involves two entity types - EMPLOYEE and COURSE
The most common relationships in E-R diagrams: 
#### 5.6.1.1 Unary (degree one)
**[Example]**
Unary Relationship
- also called as recursive relationship
a one-to-one relationship between instances of the PERSON entity type


<center><img src = '/img/CN_ISE375/ER3.png' width = 350></center>
Is_married_to -each person may be currently married to one other person
Manages – A manger manages other many employees

#### 5.6.1.2 Binary (degree two)
**[Example]**
Binary Relationship
- a relationship between instances of two entity types
The most common type of relationship encountered in data modeling

<center><img src = '/img/CN_ISE375/ER4.png' width = 350></center>

An employee is assigned one parking place, and each parking place is assigned to one employee (one-to-one).
A product line may contain several products, and each product belongs to only one product line (one-to-many).
A student may register for more than one course and that each course may have many student registrants (many-to-many) .

#### 5.6.1.3 Ternary (degree three)
**[Example]**
Ternary Relationship
Ternary relationship is a simultaneous relationship among instances of three entity types
Supplies tracks the quantity of a given part that is shipped by a particular vendor to a selected warehouse
Each entity may be a one or a many participant in a ternary relationship (many to many)


## 5.7 Cardinality and Modality

<center><img src = '/img/CN_ISE375/ER6.png' width = 350></center>

### 5.7.1 Minimum and Maximum Cardinalities

Minimum cardinality of a relationship is the minimum number of instances of entity B that may be associated with each instance of entity A
If the minimum number of DVDs available for a movie is zero, then DVD is an optional participant in the Is_stocked_as relationship

<center><img src = '/img/CN_ISE375/ER7.png' width = 350></center>


### 5.7.2 Associative Entities
If we also need to know which price quote is in effect for each part. This additional data requirement necessitates that the relationship between VENDOR and PART be transformed into an associative entity

<center><img src = '/img/CN_ISE375/ER8.png' width = 350></center>

**[Example]**
<center><img src = '/img/CN_ISE375/ER.png' width = 350></center>

---

# Lecture 6 DETERMINING SYSTEM REQUIREMENTS 


At the end of the systems planning of the SDLC. A project is initiated and planned, and project managers begin determining what the new system should do (determining system requirements)
- Analysts gather information on what the system should do from as many sources. 
- Such sources include users of the current system, reports, forms, and procedures
- Determining system requirements + requirement structuring are needed to handle for large data

**Structuring:** order the system requirements  into tables, diagrams, and other formats that make them easier to translate into technical system specifications

## 6.1 Interviewing

The primary deliverables from requirements determination 
The types of information gathered during the determination process, 

**The information can take many forms:**
transcripts of interviews;  notes from observation and analysis of documents; 
sets of forms, reports, job descriptions, computer-generated output such as system prototypes


Open-ended Q + Closed-ended Q + Observing users in their work environment



## 6.2 Joint application design (JAD)

JAD started in the late 1970s at IBM 
It aims to bring together the key users, managers, and systems analysts involved in the analysis of a current system

Very effective way to collect system requirements - Having all the key people together in one place at one time allows analysts to see the areas of agreement and the areas of conflict
Meeting with all these important people for over a week of intense sessions allows the opportunity to resolve conflicts or to understand why a conflict may not be simple to resolve.
JAD sessions are usually conducted in a location away from where the people involved normally work, in order to limit distractions and help participants better concentrate on systems analysis

**JAD session leader:**
Has been trained in group management and facilitation as well as in systems analysis 
Organizes and runs the JAD. 
Sets the agenda and sees that it is met
Remain neutral on issues and does not contribute ideas or opinions
Concentrates on keeping the group on the agenda, resolving conflicts and disagreements, and soliciting all ideas.

**Users:**
They are the only ones who clearly understand what it means to use the system on a daily basic (detail of the system)

**Managers:**
insight into new organizational directions, motivations for and organizational impacts of systems, and support for requirements determined during the JAD (nig direction of the system)

**Sponsor:**
Because of its high expense, a JAD must be sponsored by someone at a relatively high level in the company such as a vice president or chief executive officer. 
If the sponsor usually attends at the beginning or the end of JAD

**Systems analysts:**
System analysts who responsible for making the new system
System analysts are there to listen and get the information from users and managers, not to run or dominate the process.

**Scribe:**
The scribe takes notes during the JAD sessions, who makes detailed notes of the happenings at a joint application design session

**Other staffs for building the systems:**
Other staffs for building the systems such as programmers, database analysts, IS planners, and data-center personnel, may attend the session
Contribute their ideas on the technical feasibility or on the technical limitations of current systems



## 6.3 Prototyping for requirement determination

Prototyping is a repetitive process in which analysts and users build an original version of an information system based on user feedback
To establish requirements for prototyping, you still have to interview users and collect documentation
Prototyping allows to quickly convert basic requirements into a working, though limited, version of the desired information system
Typically, seeing verbal descriptions of requirements converted into a physical system leads the users to observe the things they don’t think of, and so it allows to modify existing requirements and generate new ones


## 6.4 Business process reengineering (BPR) for System Requirements 

The overall process are replaced with radically new methods is business process reengineering (BPR) to achieve breakthrough improvements in products and services.

These ways may be radically different from how things are done currently, and the payoffs may be enormous
E.g. Fewer people are needed to do work; relationships with customers may improve dramatically; and processes become much more efficient and effective; all of which can result in increased profits.


**Steps of BPR:**
Identifying Processes to Reengineering
identify specific activities that can be radically improved through reengineering
Conduct disruptive Technologies 


Disruptive technologies enable the breaking of long-held business rules that inhibit organizations from making radical business changes.

**[Example]** 
Toyota is using production schedule databases and electronic data interchange (EDI)—an information system that allows companies to link their computers directly to suppliers—to work with its suppliers as one company, and it breaks the long-held rules of Toyata.

Suppliers do not wait until toyata sends them a purchase order for more parts but simply monitor inventory levels and automatically send shipments as needed. 

---

# Lecuture 7 SYSTEMS IMPLEMENTATION AND OPERATION

Systems implementation and operation is made up of seven major activities:
Coding 
Testing 
Installation 
Documentation
Training 
Support 
Maintenance


## 7.1 Coding 
Coding is the process of turning the physical design specifications into working computer code by the programming team. Modern programming languages, such as Visual Basic, are said to be largely self-documenting


## 7.2 Testing 
It can begin and proceed in parallel with the coding process.
What type of test was conducted? What test data were used? How did the system handle the test? How were the testing results?

Software application testing covers several types of tests. Tests can be done with or without executing the code, and they may be manual or automated. 

<center><img src = '/img/CN_ISE375/L7Test.png' width = 350></center>

<center><img src = '/img/CN_ISE375/L7SA.png' width = 350></center>

Inspections are formal group activities in which participants manually examine code for occurrences of well known errors. 

1. Syntax checking is typically done by a compiler. Errors in syntax are uncovered, but the code is not executed. For the other three automated techniques, the code is executed.

2. Structured walkthroughs is a static testing technique performed in an organized manner between a group of peers to review and discuss the technical aspects of software development process.  The purpose of a walkthrough is to detect errors, not to correct them. It is the programmer’s job to correct the errors discovered in a walkthrough

3. Desk checking is an informal process who understands the logic of the program works through the code with a paper and pencil. The reviewer acts as the computer, manually checking each step and its results for the entire set of computer instructions.

4. In unit testing, each module (roughly a section of code that performs a single function) is tested alone in an attempt to discover any error. There are two approaches to unit testing: black-box and white-box.
Black-box testing is the most commonly used. In this case, the test plan is developed
directly from the program specification: Each item in the program specification
becomes a test, and several test cases are developed for it. 
White-box testing is reserved for special circumstances in which the tester wants to review the actual program code, usually when complexity is high.

Combining modules and testing them is called integration testing. Integration testing is gradual. First you test the highest level, or coordinating module, and only one of its subordinate modules.

In system testing, individual modules and programs get tested many times,  the interfaces between modules and programs are also tested

### 7.2.1 Procedures
A test plan can be done by a set of test cases, each of which must be carefully documented
A test case is a specific that represent a typical, critical, or abnormal use of the system.
The testing summary indicates:
Why the results were different and what, if anything, should be done to change the software.
Emphasis on how the actual results differed from the expected results
Suggest the need for retesting, possibly introducing new tests necessary to discover the source of the differences. 



<center><img src = '/img/CN_ISE375/L7SAF.png' width = 350></center>


## 7.3 Installation
Installation is the process which the current system is replaced by the new system, or develop a new system.

User guides provide information on how to use the new system. The training plan is a strategy for training users for quick learning. The installation plan states when, how and what for installation state. It includes conversion of existing data, software, documentation, and work procedures to those consistent with the new system. 

<center><img src = '/img/CN_ISE375/L7CTI.png' width = 350></center>

Direct installation - Changing over from the old information system to a new one by turning off the old system when the new one is turned on



<center><img src = '/img/CN_ISE375/L7Install.png' width = 350></center>

Parallel installation - Running the old information system and the new one at the same time until management decides the old system can be turned off

<center><img src = '/img/CN_ISE375/L7Install2.png' width = 350></center>


Single-location installation - Trying out a new information system at one site and using the experience to decide if and how the new system should be deployed throughout the organization.

<center><img src = '/img/CN_ISE375/L7Install3.png' width = 350></center>


Phased installation - Changing from the old information system to the new one incrementally, starting with one or a few functional components

<center><img src = '/img/CN_ISE375/L7Install4.png' width = 350></center>



### 7.3.1 Procedures

Installation is the process of moving from the current information system to the new one is called 
Four different approaches to installation:
Direct 
Parallel 
Single location 
Phased


## 7.4 Documenting the System
- Prepare documents that reveal all of the important information about this system during its development and implementation – for future uses and current references
- Two audiences for this final documentation  (1) the information systems personnel who will maintain the system throughout its productive life, and (2) the people who will use the system as part of their daily lives

Every information systems development project is unique and will generate its own unique documentation.
The format and content of the documentation may be mandated by the organization you work for.

Documentation can be divided into two basic types:
system documentation
user documentation


- System documentation records detailed information about a system’s design specifications, its internal workings, and its functionality. System documentation can be further divided into internal and external documentation.
Internal documentation - System documentation that is part of the program source code or is generated at compile time.


1. External documentation - System documentation that includes the outcome of structured diagramming techniques such as data-flow and entity-relationship diagrams.
External documentation can provide useful information to the primary users of system documentation—maintenance programmers. For example, data-flow diagrams provide a good overview of a system’s structure. 
2. User documentation - Written or other visual information about how an application system works, and how to use it. (like a Manuel)
System documentation vs User documentation
Whereas system documentation is intended primarily for maintenance programmers, user documentation is intended mainly for users (how to use a system). 

> User documentation consists of written or other visual information about an application system -  how it works, and how to use it (like a user manual)
User documentation is an investment that reduces training and consultation costs

**[Example]** 
An online user documentation for Microsoft Word appears. The documentation lists a series of training courses available for users of the latest version of Word. 


- Other types of user documentation include a quick reference guide, user’s guide, release description, system administrator’s guide, and acceptance sign-off.

1. Reference guides are great for specific information but are not good for using the broader picture to show how to perform all the steps for a given task. Reference guides provide essential information about operating a system in a short, concise format.
Often printed on index cards or as small books and mounted the computer terminal – quick search
2. Procedures manuals describe how to perform business tasks (e.g., printing a
monthly report, taking a customer order). Each item in the procedures manual typically
guides the user through a task that requires several functions or steps in the
system. Therefore, each entry is typically much longer than an entry in a reference
document.
3. Tutorials teach people how to use major components of the system (e.g., an
introduction to the basic operations of the system). Each entry in the tutorial is typically longer still than the entries in procedures manuals, and the entries are usually designed to be read in sequence, whereas entries in reference documents and procedures manuals are designed to be read individually.



## 7.5 Training
Provide training and support to users throughout the organization for the new system
Provide courses on Microsoft Windows and Office in organization-wide training facilities
Centralized information system training facilities with specialized staff who can help with training and support issues.


Many studies show that training is effective if users know the system can be a cost effective way to increase productivity, and how to install hardware and software upgrades
Therefore, the list of potential topics of training nowaday:
Use of the system (e.g., how to enter a class registration request) 
General computer concepts (e.g., computer files and how to copy them) 
Information system concepts (e.g., batch processing) 
System management (e.g., how to request changes to a system) 
System installation (e.g., how to reconcile current and new systems during phased installation)

Software help components -One common type is called an electronic performance support system (EPSS)
EPSS are online help systems that go beyond simply providing help—they embed training directly into a software package
EPSS can be an online tutorial, provide hypertext-based access or consist of an expert system shell that acts as a coach. 
The main idea behind the development of an EPSS is that the user never has to leave the application to get the benefits of training.  (whenever u need, u can learn)
EPSS is referred to as “just-in-time knowledge.”

### 7.5.1 supporting users

Automating Support
Common methods for automating support include online support forums (on private websites) and voice-response systems.
Online support forums provide users access to information on new releases, bugs, and tips for more effective usage.
Voice-response systems allow users to navigate option menus that lead to prerecorded messages about usage, problems, and workarounds. 
(Internal e-mail and instant messaging can be used to support such capabilities within an organization.)




<center><img src = '/img/CN_ISE375/L7DT.png' width = 350></center>

Evaluate  team members, reassign most to other projects, and perhaps terminate others
Notify all of the affected parties that the development project is ending and that you are now switching to operation and maintenance mode
Conduct postproject reviews with both your management and your customers. Postproject reviews follow formal procedures
Closing out the customer contract. Any contract that has been in effect between you and your customers during the project must be completed (legal issue). This may involve a formal “signing-off” by the clients that your work is complete and acceptable. 


## 7.6 Maintenance
Maintaining an information system is the process of returning to the beginning of the SDLC and repeating development steps, focusing on the needs for system change, until the change is implemented. (similar as developing a new system)

**Four activities occur within maintenance:**
Obtaining maintenance requests 
Transforming requests into changes 
Designing changes 
Implementing changes

1. Corrective maintenance refers to changes made to repair defects in the design, coding, or implementation of the system. E.g., if you purchase a new home, corrective maintenance would involve repairs things that had not worked
When corrective maintenance problems arise, they are typically urgent and need to be resolved to curtail possible interruptions in normal business activities

2. Adaptive maintenance involves making changes to an information system to evolve its functionality to migrate it to a different operating environment. E.g. Within a home, adaptive maintenance might be adding storm windows to improve its energy efficiency. 
Adaptive maintenance is usually less urgent than corrective maintenance because business and technical changes typically occur over some period of time.

3. Perfective maintenance involves making enhancements to improve processing performance, increase interface usability, or to add . E.g. In our home example, perfective maintenance would be adding a new room. Many system professionals feel that perfective maintenance is not really maintenance but new development.

4. Preventive maintenance involves changes made to a system to reduce the chance of future system failure. E.g. In our home example, preventive maintenance could be painting the exterior to better protect the home from severe weather conditions. 
*Adaptive, perfective, and preventive maintenance activities can lead to corrective maintenance activities if not carefully designed and implemented.



Actually maintenance is basically a subset of the activities of the entire development process, the deliverables are the development of a new version of the software
new versions of all design documents and training materials


### 7.6.1 Cost

Numerous factors influence the maintainability of a system:
1. Latent defects: This is the number of unknown errors existing in the system after it is installed (need corrective maintenance ). The number of latent defects in a system influences most of the costs associated with maintaining a system

2. Number of customers for a given system: 
In general, the greater the number of customers, the greater the maintenance costs. For example, if a system has only one customer, problem and change requests will come from only one source. 

2. Quality of system documentation: 
Quality documentation makes it easier to find code that needs to be changed and to understand how the code needs to be changed. Good documentation also explains why a system does what it does and why alternatives were not feasible, which saves wasted maintenance efforts.


4. Tools for documentation: Good Tools that can automatically produce system documentation can also lower maintenance costs. 

5. Maintenance personnel: 
In some organizations, the best programmers are assigned to maintenance. Highly skilled programmers are needed because the maintenance programmer is typically not the original programmer and must quickly understand and carefully change the software.

6. Well-structured programs: 
Well-designed programs are easier to understand and fix.


### 7.6.2 Measuring Maintenance Effectiveness

1. This measure is referred to as the mean time between failures (MTBF). 
MTBF is a measurement of error occurrences that can be tracked over time to indicate the quality of a system.

MTBF measures the average length of time between the identification of one system failure until the next. Over time, you should expect the MTBF value to increase rapidly after a few months of the system. 

<center><img src = '/img/CN_ISE375/L7MTDF.png' width = 350></center>

$$
\text { MTBF }=\frac{\text { Total operating time }}{\text { Number of failures }}
$$

**[Example]**
There is a factory producing lens with 20 machines operated and run 24-hours a day, 7 days a week moving parts around the factory.
Over the last four weeks, there have been 50 different issues with individual machine, requiring a total of 200 repair hours to get them up and running again to produce lens.

Uptime of machines = 4 weeks x 7 days x 24 hours x 20 machines = 13,440 hours 

the 200 hours of repair time = 13,440 hours of uptime, with 50 failures in total.
MTBF = 13,440 hours/50 failures = 268.8 hours


2. Type of failure
logging the types of failures provides a clear picture of where, when, and how failures occur.

**[Example]**
Knowing that a system repeatedly fails can provide invaluable information to the maintenance personnel. Were the users adequately trained? Is there something unique about this user? Is there something unique about an installation that is causing the failure? What activities were being performed when the system failed?




---

# REFERENCES

Alan Dennis, Barbara Haley Wixom, Roberta M. Roth. Systems analysis and design –5th ed.