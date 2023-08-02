---
title: COMP2411 Database Systems
date: 2022-12-20
updated: 2023-06-14
tags: [2022, Course Notes, Computer Science] 
categories: "Course Notes"
keywords:
description: The overview of course COMP2411 Database Systems
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
---


<span style = 'font-family: Times New Roman'>

> 📢 Disclaimer
> Copyright © [The Hong Kong Polytechnic University, Faculty of Engineering, Department of Computing](https://www.polyu.edu.hk/comp/)
> The lecture notes is for reference only, permission is hereby granted, free of charge, to any person obtaining a copy of this documentation file, to deal in the Page without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Page is furnished to do so.
> The authors or copyright holders are not be liable for any claim, damages or other liabillty, whether in an action of contract, tort or otherwise, arising from, out of or in connection with or the use or other dealings in the Page.


# Summary 
ER model: characterize relationships among entities
Relational model: transform from ER diagram to tables
SQL: language for writing queries
Relational Algebra: logical way to represent queries
Normal Forms: how to design good tables
File Organization: provide file level structure to speed up query (Applications of Index, B+ Tree)
Query Optimization: transform queries into more efficient ones (Calculation, Optimisation graph)
Transactions and Concurrency Control: handle concurrent operations and guarantee correctness of the database

---
<!-- 
TABLE OF CONTENT

- [Summary](#summary)
- [Chapter 1: Database Systems](#chapter-1-database-systems)
  - [1. Introduction](#1-introduction)
  - [2. Database Architecture (1-tier,2-tier,3-tier)](#2-database-architecture-1-tier2-tier3-tier)
  - [3. 3-level Architecture/Three schema Architecture](#3-3-level-architecturethree-schema-architecture)
    - [1. Internal](#1-internal)
    - [2. Conceptual](#2-conceptual)
    - [3. External](#3-external)
    - [Mapping](#mapping)
    - [Data Independence](#data-independence)
      - [1. Logical Data Independence](#1-logical-data-independence)
      - [2. Physical Data Independence](#2-physical-data-independence)
  - [4. Data Model](#4-data-model)
  - [5. DBMS Language](#5-dbms-language)
    - [5.1 Data Definition Language (DDL)](#51-data-definition-language-ddl)
    - [5.2 Data Manipulation Language (DML)](#52-data-manipulation-language-dml)
  - [6. Data model Schema and Instance](#6-data-model-schema-and-instance)
  - [7. Basic concepts and terminologies](#7-basic-concepts-and-terminologies)
- [Chapter 2: Entity-Relationship (ER) Model](#chapter-2-entity-relationship-er-model)
  - [1. Components of ER diagram](#1-components-of-er-diagram)
    - [1. Entity](#1-entity)
      - [1.1 Weak Entity](#11-weak-entity)
    - [2. Attribute](#2-attribute)
      - [a. Key Attribute](#a-key-attribute)
      - [b. Composite Attribute](#b-composite-attribute)
      - [c. Multivalued Attribute](#c-multivalued-attribute)
      - [d. Derived Attribute](#d-derived-attribute)
    - [3. Structural Constraint of relationship: Cardinality ratio (of a binary relationship) V.S. (Min, Max)](#3-structural-constraint-of-relationship-cardinality-ratio-of-a-binary-relationship-vs-min-max)
        - [Relationship V.S. Relationship Sets](#relationship-vs-relationship-sets)
      - [Cardinality ratio](#cardinality-ratio)
        - [a. One-to-One Relationship (1:1)](#a-one-to-one-relationship-11)
        - [b. One-to-many relationship (1:N)](#b-one-to-many-relationship-1n)
        - [c. Many-to-one relationship (N:1)](#c-many-to-one-relationship-n1)
        - [d. Many-to-many relationship (M:N)](#d-many-to-many-relationship-mn)
      - [Participation constraint (on each participating entity set or type)](#participation-constraint-on-each-participating-entity-set-or-type)
  - [Higher degree of relationship](#higher-degree-of-relationship)
  - [2. Notation of ER diagram](#2-notation-of-er-diagram)
  - [3. ER Design Issues](#3-er-design-issues)
    - [1) Use of Entity Set vs Attributes](#1-use-of-entity-set-vs-attributes)
    - [2) Use of Entity Set vs. Relationship Sets](#2-use-of-entity-set-vs-relationship-sets)
    - [3) Use of Binary vs n-ary Relationship Sets](#3-use-of-binary-vs-n-ary-relationship-sets)
    - [4) Placing Relationship Attributes](#4-placing-relationship-attributes)
  - [4. Keys](#4-keys)
    - [1. Primary Keys](#1-primary-keys)
    - [2. Candidate Keys](#2-candidate-keys)
    - [3. Super Keys](#3-super-keys)
    - [4. Foreign Keys](#4-foreign-keys)
  - [5. Generalization](#5-generalization)
  - [6. Specialization](#6-specialization)
  - [7. Aggregation](#7-aggregation)
  - [8. Reduction of ER diagram to Table/ ER diagram V.S.](#8-reduction-of-er-diagram-to-table-er-diagram-vs)
    - [Relational Schema](#relational-schema)
      - [Method 1](#method-1)
      - [Method 2](#method-2)
  - [9. Relationship of higher degree](#9-relationship-of-higher-degree)
- [Chapter 3: SQL](#chapter-3-sql)
  - [Examples](#examples)
  - [SELECT `DATA (from bottom to top) SELECT IS THE COLUMN RESULT`](#select-data-from-bottom-to-top-select-is-the-column-result)
    - [1. DISTINCT](#1-distinct)
    - [2. AND/OR/NOT](#2-andornot)
    - [3. ORDER BY](#3-order-by)
    - [4. IS NULL/ IS NOT NULL](#4-is-null-is-not-null)
    - [5. TOP](#5-top)
    - [6. MIN MAX](#6-min-max)
    - [7. COUNT/AVG/SUM](#7-countavgsum)
    - [8. LIKE](#8-like)
    - [9. IN](#9-in)
    - [10. BETWEEN..AND/ NOT BETWEEN..AND](#10-betweenand-not-betweenand)
    - [11. AS](#11-as)
    - [12. ALL and ANY](#12-all-and-any)
  - [AGGREGATE](#aggregate)
    - [13. GROUP BY](#13-group-by)
    - [14. HAVING (with aggregate functions only)](#14-having-with-aggregate-functions-only)
  - [JOIN](#join)
  - [UNION](#union)
  - [INSERT INTO `DATA (from top to bottom)`](#insert-into-data-from-top-to-bottom)
  - [Lab Java](#lab-java)
  - [2/11 Discussion](#211-discussion)
- [Chapter 4: Relational Model Concept](#chapter-4-relational-model-concept)
  - [1. Relational Algebra](#1-relational-algebra)
    - [1. Select Operation: SIGMA](#1-select-operation-sigma)
    - [2. Project Operation: PI](#2-project-operation-pi)
    - [3. Union Operation (or):](#3-union-operation-or)
    - [4. Set Intersection (and):](#4-set-intersection-and)
    - [5. Set Difference:](#5-set-difference)
    - [6. Cartesian product |\>\<|](#6-cartesian-product-)
  - [2. Join Operations:](#2-join-operations)
    - [1. Natural Join](#1-natural-join)
    - [2. Outer Join:](#2-outer-join)
      - [a. Left outer join:](#a-left-outer-join)
      - [b. Right outer join:](#b-right-outer-join)
      - [c. Full outer join:](#c-full-outer-join)
    - [3. Equi join:](#3-equi-join)
  - [Summary](#summary-1)
- [Chapter 5: Integrity Constraints (ICs) and Normal Forms](#chapter-5-integrity-constraints-ics-and-normal-forms)
  - [1. Domain Constraint](#1-domain-constraint)
  - [2. Entity Integrity Constraint](#2-entity-integrity-constraint)
  - [3. Referential Integrity Constraint](#3-referential-integrity-constraint)
  - [4. Key Constraint](#4-key-constraint)
  - [Functional Dependency and Normal Forms](#functional-dependency-and-normal-forms)
  - [Types of Functional Dependency](#types-of-functional-dependency)
    - [1. Trivial functional dependency](#1-trivial-functional-dependency)
    - [2. Non-trivial functional dependency](#2-non-trivial-functional-dependency)
    - [Inference Rules for FDs](#inference-rules-for-fds)
      - [1. Reflexive Rule (IR1)](#1-reflexive-rule-ir1)
      - [2. Augmentation Rule (IR2)](#2-augmentation-rule-ir2)
      - [3. Transitive Rule (IR3)](#3-transitive-rule-ir3)
      - [4. Union Rule (IR4)](#4-union-rule-ir4)
      - [5. Decomposition Rule (IR5)](#5-decomposition-rule-ir5)
      - [6. Pseudo transitive Rule (IR6)](#6-pseudo-transitive-rule-ir6)
  - [Types of Normal Forms:](#types-of-normal-forms)
    - [1NF](#1nf)
      - [Problems](#problems)
      - [Solution](#solution)
    - [2NF](#2nf)
    - [3NF (Good Design!)](#3nf-good-design)
    - [BCNF](#bcnf)
- [Chapter 6: File Organization and Indexing](#chapter-6-file-organization-and-indexing)
  - [File Organization](#file-organization)
  - [1. Unordered File](#1-unordered-file)
    - [1.1 Pile File Method:](#11-pile-file-method)
  - [2. Ordered File (Sequential File Organization)](#2-ordered-file-sequential-file-organization)
    - [2.1 Sorted File Method:](#21-sorted-file-method)
  - [3. Heap Files (Unordered)](#3-heap-files-unordered)
  - [4. Hashed Files](#4-hashed-files)
    - [4.1 Static External Hashing](#41-static-external-hashing)
      - [4.1.1 Collisions problem](#411-collisions-problem)
        - [4.1.1.1 Opening Addressing: Linear Probing](#4111-opening-addressing-linear-probing)
        - [4.1.1.2 Opening Addressing: Quadratic Probing](#4112-opening-addressing-quadratic-probing)
      - [4.1.2 Overflow chaining/ Overflow handling](#412-overflow-chaining-overflow-handling)
    - [4.2 Dynamic And Extendible Hashing](#42-dynamic-and-extendible-hashing)
  - [5. Indexing](#5-indexing)
    - [5.1 Ordered indices](#51-ordered-indices)
      - [5.1.1 Single level index/ Sparse indexing/ Primary index (Ordered)](#511-single-level-index-sparse-indexing-primary-index-ordered)
        - [5.1.1.1 Dense index](#5111-dense-index)
        - [5.1.1.2 Sparse index](#5112-sparse-index)
      - [5.2.1 Clustering index  (Ordered)](#521-clustering-index--ordered)
      - [5.3.1 Secondary index (Non-ordered)](#531-secondary-index-non-ordered)
      - [5.4.1 Multi-level index (primary, secondary, clustering)](#541-multi-level-index-primary-secondary-clustering)
      - [5.4.2 Using B Trees and B+ Trees as Dynamic Multi-level Indexes](#542-using-b-trees-and-b-trees-as-dynamic-multi-level-indexes)
        - [Insertion](#insertion)
        - [Delection](#delection)
    - [Denormalization](#denormalization)
- [Chapter 7: Query Processing \& Query Optimization](#chapter-7-query-processing--query-optimization)
  - [1. Translating SQL Queries into Relational Algebra](#1-translating-sql-queries-into-relational-algebra)
  - [2. Search Methods for Selection](#2-search-methods-for-selection)
    - [Linear search (brute force)](#linear-search-brute-force)
    - [Binary search](#binary-search)
    - [Using a primary index or hash key to retrieve a single record](#using-a-primary-index-or-hash-key-to-retrieve-a-single-record)
    - [Using a primary index to retrieve multiple records](#using-a-primary-index-to-retrieve-multiple-records)
    - [Using a clustering index to retrieve multiple records](#using-a-clustering-index-to-retrieve-multiple-records)
  - [3. Calculation](#3-calculation)
    - [a. Nested-loop join](#a-nested-loop-join)
    - [b. Block nested-loop join](#b-block-nested-loop-join)
    - [c. Merge join](#c-merge-join)
    - [d. Hash join](#d-hash-join)
  - [4. Heuristic Algebraic Optimization Algorithm](#4-heuristic-algebraic-optimization-algorithm)
- [Chapter 8: Transactions and Concurrency Control](#chapter-8-transactions-and-concurrency-control)
  - [1. Transaction](#1-transaction)
    - [1.1 Property of Transaction](#11-property-of-transaction)
    - [1.2 Transaction Status](#12-transaction-status)
  - [2. Schedule](#2-schedule)
  - [Example](#example)
  - [3. Schedules Classified on Recoverability](#3-schedules-classified-on-recoverability)
    - [3.1 Non-recoverable schedule](#31-non-recoverable-schedule)
    - [3.2 Recoverable schedule with cascaded rollback](#32-recoverable-schedule-with-cascaded-rollback)
    - [3.3 Cascadeless schedule](#33-cascadeless-schedule)
    - [3.4 Strict schedules](#34-strict-schedules)
  - [Example](#example-1)
  - [4. Schedules Classified on Serializability](#4-schedules-classified-on-serializability)
    - [4.1 Conflict Serializable Schedule](#41-conflict-serializable-schedule)
    - [4.2 Conflict Equivalent](#42-conflict-equivalent)
    - [4.3 Result equivalent](#43-result-equivalent)
  - [5. Test of Serializability](#5-test-of-serializability)
    - [5.1 Non-serializable schedule](#51-non-serializable-schedule)
    - [5.2 Serializable schedule](#52-serializable-schedule)
  - [Example](#example-2)
  - [NOT YET MENTIONED IN TGE LECTURE](#not-yet-mentioned-in-tge-lecture)
  - [View Serializability](#view-serializability)
  - [View Equivalent](#view-equivalent)
  - [Failure Classification](#failure-classification)
    - [1. Transaction failure](#1-transaction-failure)
    - [2. System Crash](#2-system-crash)
    - [3. Disk Failure](#3-disk-failure)
  - [Log-Based Recovery](#log-based-recovery)
    - [Recovery using Log records](#recovery-using-log-records)
  - [Checkpoint](#checkpoint)
    - [Recovery using Checkpoint](#recovery-using-checkpoint)
  - [Deadlock in DBMS](#deadlock-in-dbms)
    - [1. Deadlock Avoidance](#1-deadlock-avoidance)
    - [2. Deadlock Detection](#2-deadlock-detection)
    - [3. Wait for Graph](#3-wait-for-graph)
    - [Deadlock Prevention](#deadlock-prevention)
      - [1. Wait-Die scheme](#1-wait-die-scheme)
      - [2. Wound wait scheme](#2-wound-wait-scheme)
- [Chapter 8: DBMS Concurrency Control](#chapter-8-dbms-concurrency-control)
  - [Concurrent Execution](#concurrent-execution)
  - [Problems with Concurrent Execution](#problems-with-concurrent-execution)
    - [1. Lost Update Problems (W-W Conflict)](#1-lost-update-problems-w-w-conflict)
    - [1. Phantom Read Problem (W-R Conflict)](#1-phantom-read-problem-w-r-conflict)
    - [2. Dirty Read/ Temporary Update Problems (W-R Conflict)](#2-dirty-read-temporary-update-problems-w-r-conflict)
    - [3. Nonrepeatable Read Problem (W-R Conflict)](#3-nonrepeatable-read-problem-w-r-conflict)
    - [Summary](#summary-2)
  - [Concurrency Control Protocols](#concurrency-control-protocols)
    - [1. Lock Based Concurrency Control Protocol](#1-lock-based-concurrency-control-protocol)
        - [3. Two-phase locking (2PL)](#3-two-phase-locking-2pl)
          - [1. Shared lock](#1-shared-lock)
          - [2. Exclusive lock](#2-exclusive-lock)
        - [(a) Basic](#a-basic)
        - [(b) Conservative](#b-conservative)
        - [(c) Strict](#c-strict)
        - [4. Strict Two-phase locking (Strict-2PL)](#4-strict-two-phase-locking-strict-2pl)
    - [2. Time Stamp Concurrency Control Protocol](#2-time-stamp-concurrency-control-protocol)
    - [3. Validation Based Concurrency Control Protocol](#3-validation-based-concurrency-control-protocol)
  - [Recovery with Concurrent Transaction](#recovery-with-concurrent-transaction)
      - [1. Selecting a victim](#1-selecting-a-victim)
      - [2. Rollback](#2-rollback)
      - [3. Starvation](#3-starvation)
- [Chapter 9:  DDT](#chapter-9--ddt)
- [Lab 1 Table Definition, Manipulation and Simple Queries](#lab-1-table-definition-manipulation-and-simple-queries)
  - [Link to SQL](#link-to-sql)
  - [Import .SQL](#import-sql)
  - [Exercise](#exercise)
  - [1.1 Common Data Types](#11-common-data-types)
  - [1.2 NULL values](#12-null-values)
  - [2.1 Inserting Tuples into Tables](#21-inserting-tuples-into-tables)
  - [2.2 Altering Tables](#22-altering-tables)
  - [3.1 Select](#31-select)
- [Lab 2 Queries, Arithmetic Expressions and Functions](#lab-2-queries-arithmetic-expressions-and-functions)
  - [1.1 Selecting Rows within a Certain Range](#11-selecting-rows-within-a-certain-range)
  - [1.2  Selecting Rows That Match a Value in  List](#12--selecting-rows-that-match-a-value-in--list)
  - [1.3 Selecting Rows That Match a Character Pattern](#13-selecting-rows-that-match-a-character-pattern)
  - [2.1 Ordering Rows](#21-ordering-rows)
  - [2.2 Ordering Rows Using Multiple Columns](#22-ordering-rows-using-multiple-columns)
  - [2.3 Ordering Rows By Columns With NULL Values](#23-ordering-rows-by-columns-with-null-values)
  - [3.1 Arithmetic Expressions](#31-arithmetic-expressions)
  - [3.2  Arithmetic Expressions with ORDER BY](#32--arithmetic-expressions-with-order-by)
  - [3.3 The NULL Function](#33-the-null-function)
  - [3.4 Column Labels](#34-column-labels)
  - [4.1 Arithmetic Functions (ROUND)](#41-arithmetic-functions-round)
  - [5.1 Character String Functions](#51-character-string-functions)
- [Lab 3 Aggregate Functions, 'Group By' and 'Having' Clauses](#lab-3-aggregate-functions-group-by-and-having-clauses)
  - [1.1 Selecting Summary Information from One Group](#11-selecting-summary-information-from-one-group)
  - [2.1 Sub-query](#21-sub-query)
  - [2.2 DISTINCT](#22-distinct)
  - [3.1 SELECTING SUMMARY INFORMATION FROM GROUPS – GROUP BY](#31-selecting-summary-information-from-groups--group-by)
  - [3.2 SPECIFYING A SEARCH-CONDITION FOR GROUPS – HAVING](#32-specifying-a-search-condition-for-groups--having)
  - [3.3  More on Sub-query](#33--more-on-sub-query)
  - [4.1 4 EFFECTS OF NULL VALUES ON GROUP FUNCTIONS](#41-4-effects-of-null-values-on-group-functions)
  - [5 FORMATING QUERY RESULTS INTO A REPORT](#5-formating-query-results-into-a-report) -->


# Lecture 1: DATABASE SYSTEMS
## 1. Introduction

The main purpose of the database is to operate a large amount of information by storing, retrieving, and managing data.

There are many dynamic websites on the World Wide Web nowadays which are handled through databases. For example, a model that checks the availability of rooms in a hotel. It is an example of a dynamic website that uses a database.

There are many databases available like MySQL, Sybase, Oracle, MongoDB, Informix, PostgreSQL, SQL Server, etc.

`Relational Database`
Relational database model has two main terminologies called instance and schema.
The instance is a table with rows or columns

There are following four commonly known properties of a relational model known as `ACID properties`, where:

A means `Atomicity`: This ensures the data operation will complete `either with success or with failure`. It follows the 'all or nothing' strategy. For example, a transaction will either be committed or will abort.

C means `Consistency`: If we perform any operation over the data, its value before and after the operation should be preserved. For example, the account balance before and after the transaction should be correct, i.e., it should remain conserved.

I means `Isolation`: There can be concurrent users for accessing data at the same time from the database. Thus, isolation between the data should remain isolated. For example, when multiple transactions occur at the same time, one transaction effects should not be visible to the other transactions in the database.

D means `Durability`: It ensures that once it completes the operation and commits the data, data changes should remain permanent.


`Cloud Database` 
Cloud database facilitates you to store, manage, and retrieve their structured, unstructured data via a cloud platform. This data is accessible over the Internet. Cloud databases are also called a database as service (DBaaS) because they are offered as a managed service.
e.g., DWS, Oracle, MS Server 

`NoSQL` 
Not only for database 
MongoDB, CouchDB, Cloudant (Document-based)
Memcached, Redis, Coherence (key-value store)
HBase, Big Table, Accumulo (Tabular)

`DBMS`, `Graph Database`, `RDBMS`...


DBMS VS RDBMS
![请添加图片描述](https://img-blog.csdnimg.cn/1edfa095d7f84e4a8f6489724fee8dc1.png)

DBMS VS File System
![请添加图片描述](https://img-blog.csdnimg.cn/8d940998b0f14f2daa54d9e367ea070a.png)


## 2. Database Architecture (1-tier,2-tier,3-tier)

**2-tier Architecture**
The 2-Tier architecture is same as basic `client-server`. In the two-tier architecture, applications on the client end can directly communicate with the database at the server side. For this interaction, API's like: ODBC, JDBC are used.
The `user interfaces and application programs` are run on the `client-side`.
The `server side` is responsible to provide the functionalities like: query processing and transaction management.
To communicate with the DBMS, client-side application establishes a connection with the server side.

![请添加图片描述](https://img-blog.csdnimg.cn/8a522e68558e462d874b19110100e9a3.png)


**3-tier Architecture**
The 3-Tier architecture contains another layer between the client and server. In this architecture, client can't directly communicate with the server.
The application on the client-end interacts with an application server which further communicates with the database system.
End user has no idea about the existence of the database beyond the application server. The database also has no idea about any other user beyond the application.
The 3-Tier architecture is used in case of large web application.

![请添加图片描述](https://img-blog.csdnimg.cn/3425fa04653545a08ede421aa8a14478.png)

## 3. 3-level Architecture/Three schema Architecture

The three schema architecture is also called `ANSI/SPARC architecture or three-level architecture`.

The main objective of three level architecture is to enable multiple users to access the same data with a personalized view while storing the underlying data only once. Thus it separates the user's view from the physical structure of the database.
 - Abstract view of the data
simplify interaction with the system
hide details of how data is stored and manipulated
- Levels of abstraction
physical/internal level: data structures; how data are actually stored
conceptual level: schema, what data are actually stored
view/external level: partial schema
- the ability to manage persistent data
- primary goal of DBMS: to provide an environment that is convenient, efficient, and robust to use in retrieving & storing data
![在这里插入图片描述](https://img-blog.csdnimg.cn/ae6817da721f439e8c3f5161cb1c5532.png)

### 1. Internal
`How data store in block`

Storage space allocations.
For Example: [B-Trees](#B-Trees), Hashing etc.
Access paths.
For Example: Specification of primary and secondary keys, indexes, pointers and sequencing.
Data compression and encryption techniques.
Optimization of internal structures.
Representation of stored fields.
![请添加图片描述](https://img-blog.csdnimg.cn/c4f0547f1a774ce2bff9c1f285712cb3.png)

### 2. Conceptual
The conceptual schema describes the design of a database at the conceptual level. Conceptual level is also known as logical level.
The conceptual schema describes the `structure of the whole database`.
The conceptual level describes what data are to be stored in the database and also describes what relationship exists among those data.
In the conceptual level, internal details such as an implementation of the data structure are hidden.
Programmers and database administrators work at this level.

![请添加图片描述](https://img-blog.csdnimg.cn/4fd2a9f600e74f48b1d54063367ca6ac.png)
### 3. External
At the external level, a database contains several schemas that sometimes called as `subschema`. The subschema is used to describe the different view of the database.
An external schema is also known as view schema.
Each view schema describes the database part that a particular user group is interested and hides the remaining database from that user group.
The view schema describes the end user interaction with database systems.
![请添加图片描述](https://img-blog.csdnimg.cn/17bde88e74204cb0a68a78877b90fc0b.png)




### Mapping
- Conceptual/ Internal Mapping

The Conceptual/ Internal Mapping lies between the conceptual level and the internal level. Its role is to define the correspondence between the records and fields of the conceptual level and files and data structures of the internal level.

- External/ Conceptual Mapping

The External/Conceptual Mapping lies between the external level and the Conceptual level. Its role is to define the correspondence between a particular external and the conceptual view.

### Data Independence
Data independence can be explained using the three-schema architecture.
Data independence refers characteristic of being able to modify the schema at one level of the database system without altering the schema at the next higher level.
There are two types of data independence:

#### 1. Logical Data Independence
Logical data independence refers characteristic of being able to change the conceptual schema without having to change the external schema.
Logical data independence is used to separate the external level from the conceptual view.
`If we do any changes in the conceptual view of the data, then the user view of the data would not be affected.`
Logical data independence occurs at the user interface level.

#### 2. Physical Data Independence
Physical data independence can be defined as the capacity to change the internal schema without having to change the conceptual schema.
`If we do any changes in the storage size of the database system server, then the Conceptual structure of the database will not be affected.`
Physical data independence is used to separate conceptual levels from the internal levels.
Physical data independence occurs at the logical interface level.



## 4. Data Model
- Object-based logical models (conceptual & view levels)
**the Entity-Relationship (ER) model -- mid 70’s**
the Semantic Data Models -- early/mid 80’s
the Object-Oriented data models -- late 80’s
- Record-based logical models (conceptual & view levels)
the Network and Hierarchical models -- 60’s
**the Relational model -- early 70’s**

An ER model is the logical representation of data as `objects and relationships` among them. These objects are known as `entities`, and `relationship` is an association among these entities. This model was designed by Peter Chen and published in 1976 papers. It was widely used in database designing. A set of `attributes` describe the `entities`. For example, student_name, student_id describes the 'student' entity. A set of the same type of `entities` is known as an `'Entity set'`, and the set of the same type of `relationships` is known as `'relationship set'`.



## 5. DBMS Language

![请添加图片描述](https://img-blog.csdnimg.cn/1c1989965ab24749b1018212870e45f4.png)

### 5.1 Data Definition Language (DDL)
- a language for defining DB schema
- Data definition language is used to `store the information of metadata` like the number of tables and schemas, their names, indexes, columns in each table, constraints, etc.


Create: It is used to create objects in the database.
Alter: It is used to alter the structure of the database.
Drop: It is used to delete objects from the database.
Truncate: It is used to remove all records from a table.
Rename: It is used to rename an object.
Comment: It is used to comment on the data dictionary.
These commands are used to update the database schema that's why they come under Data definition language.


### 5.2 Data Manipulation Language (DML)
DML stands for Data Manipulation Language. It is used for `accessing and manipulating data` in a database. It handles user requests. 
- an important subset for retrieving data is called **Query Language**
- two types of DML: procedural (specify “what” & “how”) vs. declarative (just specify “what”)

Select: It is used to retrieve data from a database.
Insert: It is used to insert data into a table.
Update: It is used to update existing data within a table.
Delete: It is used to delete all records from a table.
Merge: It performs UPSERT operation, i.e., insert or update operations.
Call: It is used to call a structured query language or a Java subprogram.
Explain Plan: It has the parameter of explaining data.
Lock Table: It controls concurrency.


## 6. Data model Schema and Instance

The data which is stored in the database at a particular moment of time is called an instance of the database.
The overall design of a database is called `schema`.
A database schema is the skeleton structure of the database. It represents the logical view of the entire database.
A schema contains schema objects like `table, foreign key, primary key, views, columns, data types, stored procedure, etc`.
A database schema can be represented by using the visual diagram. That diagram shows the database objects and relationship with each other.



## 7. Basic concepts and terminologies
- instance
the collection of data (information) stored in the DB at a particular moment (ie, a snapshot)
- scheme/schema
the overall structure (design) of the DB -- relatively static


![请添加图片描述](https://img-blog.csdnimg.cn/d24feb5bc6044c6d9fe473facb1df78c.png)




---
# Lecture 2: ENTITY-RELATIONSHIPS (ER) MODEL
## 1. Components of ER diagram
![请添加图片描述](https://img-blog.csdnimg.cn/0ba95c4b545049f3bf297cc6df6b5a56.png)

### 1. Entity
An entity may be any object, class, person or place. In the ER diagram, an entity can be represented as rectangles.
Consider an organization as an example- manager, product, employee, department etc. can be taken as an entity.


![请添加图片描述](https://img-blog.csdnimg.cn/2eae7a0d5cdb4d24a93e1bf340824dbc.png)

#### 1.1 Weak Entity
An entity that depends on another entity called a `weak entity`. The weak entity doesn't contain any key attribute of its own. The weak entity is represented by a double rectangle.
   
![请添加图片描述](https://img-blog.csdnimg.cn/a42c55ee0cbe4535b3ba60c01544662d.png)

`There is no primary key in weak attribute (non-key attribute)`

![请添加图片描述](https://img-blog.csdnimg.cn/b1a7b9da744d414da65de9ac90c5535d.png)
![请添加图片描述](https://img-blog.csdnimg.cn/0cfa7ea54afc4c70a11017f718374be9.png)


### 2. Attribute
The attribute is used to describe the property of an entity. Eclipse is used to represent an attribute.
For example, id, age, contact number, name, etc. can be attributes of a student.



#### a. Key Attribute
The key attribute is used to represent the main characteristics of an entity. It represents a primary key. The key attribute is represented by an ellipse with the text underlined.

![请添加图片描述](https://img-blog.csdnimg.cn/12b8fe95b4fa42b49ee336a97d82326c.png)
#### b. Composite Attribute
An attribute that composed of many other attributes is known as a composite attribute. The composite attribute is represented by an ellipse, and those ellipses are connected with an ellipse.
![请添加图片描述](https://img-blog.csdnimg.cn/ce223e0b6bef4386a772f82847c9234e.png)
#### c. Multivalued Attribute
An attribute can have more than one value. These attributes are known as a multivalued attribute. The double oval is used to represent multivalued attribute. For example, a student can have more than one phone number.

![请添加图片描述](https://img-blog.csdnimg.cn/ee377379251c4d0baa31898b577f669c.png)




![请添加图片描述](https://img-blog.csdnimg.cn/18c4de3d2ec54aaab68b0d3bd75b469c.jpeg)

SIMPLE: SSN, Sex
COMPOSITE: Address(Apt#, Street, City, State, ZipCode, Country) or Name(FirstName, MiddleName, LastName)
MULTI-VALUED: multiple values;  Color of a CAR, denoted as {Color}.

COMPOSITE and MULTI-VALUED may be generally `nested`.
{PreviousDegrees(College, Year, Degrees, Field)}


#### d. Derived Attribute
An attribute that can be derived from other attribute is known as a derived attribute. It can be represented by a dashed ellipse. For example, A person's age changes over time and can be derived from another attribute like Date of birth.

![请添加图片描述](https://img-blog.csdnimg.cn/642b402feee144aca2be0b6f1e8b1a14.png)


### 3. Structural Constraint of relationship: Cardinality ratio (of a binary relationship) V.S. (Min, Max)

##### Relationship V.S. Relationship Sets
- Relationship: related two or more distinct entities with a specific meaning
EMPLOYEE John Smith `works on` the PROJECT 'solar', or EMPLOYEE Franklin Wong `manages` the Research DEPARTMENT.
- Relationship Set: Relationships of the same type are grouped together.
the `WORKS_ON` relationship type in which EMPLOYEES and PROJECTS participate; the `MANAGES` relationship type in which EMPLOYEE and DEPARTMENT.

Both MANAGES and WORKS_ON are `binary` relationships, both of which can `same participate` in entity sets/ types.

#### Cardinality ratio

A relationship is used to describe the relation between entities. Diamond or rhombus is used to represent the relationship.

##### a. One-to-One Relationship (1:1)
When only one instance of an entity is associated with the relationship, then it is known as one to one relationship.
For example, A female can marry to one male, and a male can marry to one female.

![](https://img-blog.csdnimg.cn/e84642800f2a4cccb9a5cec09e69439a.png)

##### b. One-to-many relationship (1:N)
When only one instance of the entity on the left, and more than one instance of an entity on the right associates with the relationship then this is known as a one-to-many relationship.
For example, Scientist can invent many inventions, but the invention is done by the only specific scientist.

![](https://img-blog.csdnimg.cn/1ac4727604e3427499f88740e352e1fa.png)

##### c. Many-to-one relationship (N:1)
When more than one instance of the entity on the left, and only one instance of an entity on the right associates with the relationship then it is known as a many-to-one relationship.
For example, Student enrolls for only one course, but a course can have many students.
![在这里插入图片描述](https://img-blog.csdnimg.cn/ae5d6b3edd8d4f2390db29f45ed93fe4.png)


##### d. Many-to-many relationship (M:N)
When more than one instance of the entity on the left, and more than one instance of an entity on the right associates with the relationship then it is known as a many-to-many relationship.
For example, Employee can assign by many projects and project can have many employees.
![在这里插入图片描述](https://img-blog.csdnimg.cn/ce737901e598431882a28f7111a31203.png)

#### Participation constraint (on each participating entity set or type)
Partial participation: min = 0, MAY NOT appears in the rows; by single line
Total participation: min > 0, MUST appears in the rows; by double line (every entity participate)


Minimum cardinality tells whether the participation is partial or total.
If minimum cardinality = 0, then it signifies partial participation.
If minimum cardinality = 1, then it signifies total participation.
Maximum cardinality tells the maximum number of entities that participates in a relationship set.


## Higher degree of relationship
Directly transformation between cardinality ratio and $(min, max)$ is not allowed.
 
`(MIN, MAX)` can be considered as how many times an entity would appear in the rows.


![请添加图片描述](https://img-blog.csdnimg.cn/49e7812ed24f48a8a45ca1b86bd24c5f.png)


![请添加图片描述](https://img-blog.csdnimg.cn/755a0f8c9a5c49e9a864430c1ca4b5e3.jpeg)




![请添加图片描述](https://img-blog.csdnimg.cn/27197a868ecc44468efe45d9174b2c96.png)

**[Examples]**

One-to-one
Many students belong to one department 
> Student ---- N ----- belongs to ----- 1 ---- Department 

Each student belongs to at one department only; Each department has at least one and more than one students
`This would be more clear, since some times when there is tertinary relationship, m:n:p is meaningless.`
> Student ---- ( 1,1 ) ----- belongs to -----( 1,N ) ---- Department 



## 2. Notation of ER diagram
![在这里插入图片描述](https://img-blog.csdnimg.cn/e2eb5f62357645f3b1075bb21708eaf8.png)


## 3. ER Design Issues
### 1) Use of Entity Set vs Attributes

The use of an entity set or attribute depends on the structure of the real-world enterprise that is being modelled and the semantics associated with its attributes. It leads to a mistake `when the user use the primary key of an entity set as an attribute of another entity set`. Instead, he should use the relationship to do so. Also, the primary key attributes are implicit in the relationship set, but we designate it in the relationship sets.

> We should not link ____ directly with other entity's attribute
### 2) Use of Entity Set vs. Relationship Sets

It is difficult to examine `if an object can be best expressed by an entity set or relationship set`. To understand and determine the right use, the user need to designate a relationship set for describing an action that occurs in-between the entities. 
> If there is a requirement of representing the object as a relationship set, then its better not to mix it with the entity set.

### 3) Use of Binary vs n-ary Relationship Sets

Generally, the relationships described in the databases are `binary relationships`. However, non-binary relationships can be represented by several binary relationships. For example, we can create and represent a ternary relationship 'parent' that may relate to a child, his father, as well as his mother. Such relationship can also be represented by two binary relationships i.e, mother and father, that may relate to their child. 
> It is possible to represent a non-binary relationship by a set of distinct binary relationships.

![请添加图片描述](https://img-blog.csdnimg.cn/79ae3260db574f8b94d6741a4dfeb9d8.jpeg)
![请添加图片描述](https://img-blog.csdnimg.cn/7b39a5f006a94e209e22b3c3af315be2.jpeg)
![请添加图片描述](https://img-blog.csdnimg.cn/0f044b8193074dec8c69d2a72febfc8e.jpeg)

![请添加图片描述](https://img-blog.csdnimg.cn/7229392e6e484153bc65254d8e5bb16d.jpeg)


### 4) Placing Relationship Attributes

The cardinality ratios can become an affective measure in the placement of the relationship attributes. So, it is better to associate the attributes of `one-to-one or one-to-many relationship sets` with any participating entity sets, instead of any relationship set. The decision of placing the specified attribute as a relationship or entity attribute should possess the charactestics of the real world enterprise that is being modelled.

For example, if there is an entity which can be determined by the combination of participating entity sets, instead of determing it as a separate entity. Such type of attribute must be associated with the many-to-many relationship sets.

> Focus on the number of determination 



## 4. Keys 

### 1. Primary Keys
The minimal attribute of candidate key, which is the first key used to identify one and only `one instance of an entity uniquely`. An entity can contain multiple keys, as we saw in the PERSON table. The key which is most suitable from those lists becomes a primary key.

![在这里插入图片描述](https://img-blog.csdnimg.cn/3f13f4f05ba04b12babd64c52104dfbc.png)

### 2. Candidate Keys 
A candidate key is an attribute or set of attributes that can `uniquely identify a tuple`.
Except for the primary key, the remaining attributes are considered a candidate key. The candidate keys are as strong as the primary key.
For example: In the EMPLOYEE table, id is best suited for the primary key. The rest of the attributes, like SSN, Passport_Number, License_Number, etc., are considered a candidate key.

![在这里插入图片描述](https://img-blog.csdnimg.cn/c0ee8279fe6040e59b06d84339c8461d.png)

### 3. Super Keys 

Super key is an attribute set that can uniquely identify a tuple. A super key is a superset of a candidate key.

![在这里插入图片描述](https://img-blog.csdnimg.cn/51675e64e0aa4d408707bb20d671c5a5.png)

For example: In the above EMPLOYEE table, for(EMPLOEE_ID, EMPLOYEE_NAME), the name of two employees can be the same, but their EMPLYEE_ID can't be the same. Hence, this combination can also be a key.

The super key would be EMPLOYEE-ID (EMPLOYEE_ID, EMPLOYEE-NAME), etc.

![请添加图片描述](https://img-blog.csdnimg.cn/daf83bd5551140eb9da2707a4303fdac.png)

Super key in the table above:
{EMP_ID}, {EMP_ID, EMP_NAME}, {EMP_ID, EMP_NAME, EMP_ZIP}....so on  
Candidate key: {EMP_ID}

To find the candidate keys, you need to see what path leads you to all attributes using the dependencies. So you are correct about A because from A you can reach B that can reach {C, D}. AB can't be considered a candidate key because it has never been mentioned in your dependencies. Another way to think about it is by remembering that candidate key is the minimum number of attributes that guarantees uniqueness in your rows. But since A is already a candidate key then AB is not minimal set. Since you only have one candidate key that's A. A is called a key attribute and all other attributes are called non-key attributes. then you decide the number of super keys by 2 to the power of number of non-key attributes (B, C, D). In this scenario you should have 8 super keys. The way to find them is simply by mashing A with all possible combinations of the non-key attributes. So your superkeys would be A, AB, AC, AD, ABC, ABD, ACD, ABCD.

<a src = 'https://stackoverflow.com/questions/30091757/find-the-superkeys'>Find the Superkeys</a>
### 4. Foreign Keys 

Foreign keys are the column of the table used to `point to the primary key of another table`.
Every employee works in a specific department in a company, and employee and department are two different entities. So we can't store the department's information in the employee table. That's why we link these two tables through the primary key of one table.
We add the primary key of the DEPARTMENT table, Department_Id, as a new attribute in the EMPLOYEE table.
In the EMPLOYEE table, Department_Id is the foreign key, and both the tables are related.
![在这里插入图片描述](https://img-blog.csdnimg.cn/f78427f27a6748e0aa80f484d76ce5f9.png)

3 more keys to go...

>  superkey 
a set of **one or more attributes** which, taken together, identify uniquely an entity in an entity set
Example:  {student ID, Name} identify a student

> candidate key
minimal set of attributes which can identify uniquely an entity in an entity set
a special case of superkey (for which no proper subset is a superkey)
Example:  student ID identify a student, but Name is not a candidate key (WHY?)
**more than candidate key, pick one as primary key**

> primary key
a candidate key chosen by the DB designer to identify an entity in an entity set


## 5. Generalization

Generalization is like a `bottom-up approach` in which two or more entities of lower level combine to form a higher level entity if they have some attributes in common.
In generalization, an entity of a higher level can also combine with the entities of the lower level to form a further higher level entity.
Generalization is more like subclass and superclass system, but the only difference is the approach. Generalization uses the bottom-up approach.
In generalization, entities are combined to form a more generalized entity, i.e., subclasses are combined to make a superclass.
For example, Faculty and Student entities can be generalized and create a higher level entity Person.

![在这里插入图片描述](https://img-blog.csdnimg.cn/d7d267d163d0438181a2f5c6a32ecaa9.png)

## 6. Specialization

Specialization is a `top-down` approach, and it is opposite to Generalization. In specialization, one higher level entity can be broken down into two lower level entities.
Specialization is used to identify the subset of an entity set that shares some distinguishing characteristics.
Normally, the superclass is defined first, the subclass and its related attributes are defined next, and relationship set are then added.
For example: In an Employee management system, EMPLOYEE entity can be specialized as TESTER or DEVELOPER based on what role they play in the company.
![在这里插入图片描述](https://img-blog.csdnimg.cn/8c7f7a3e3ad14ad2806c85fd1df9d714.png)


## 7. Aggregation

In aggregation, the relation between two entities is treated as a single entity. In aggregation, relationship with its corresponding entities is aggregated into a higher level entity.

For example: Center entity offers the Course entity act as a single entity in the relationship which is in a relationship with another entity visitor. In the real world, if a visitor visits a coaching center then he will never enquiry about the Course only or just about the Center instead he will ask the enquiry about both.

![在这里插入图片描述](https://img-blog.csdnimg.cn/3a4b87f49d9a4a65926c7b9b5c0be530.png)


## 8. Reduction of ER diagram to Table/ ER diagram V.S. 

The database can be represented using the notations, and these notations can be reduced to a collection of tables.
In the database, every entity set or relationship set can be represented in tabular form.

![在这里插入图片描述](https://img-blog.csdnimg.cn/fd5a9b188d6b4026be5b2550bfb7dc60.png)

> In the student table, a hobby is a multivalued attribute. So it is not possible to represent multiple values in a single column of STUDENT table.

![在这里插入图片描述](https://img-blog.csdnimg.cn/e29a6a8a4f6746518eec741ed7102f0d.png)

`Don't have to link the arrow, since it is not the referential constraints`
> Entity: EMPLOYEE, DEPARTMENT, PROJECT, DEPENDENT
> Relationship: DEPT_LOCATIONS, WORKS_ON -> primary keys, and non-key attributes

### Relational Schema

#### Method 1
![请添加图片描述](https://img-blog.csdnimg.cn/f7558474680f472e92367b31c2481e46.png)

![请添加图片描述](https://img-blog.csdnimg.cn/3d7c1edb89994ac7bd01661d243c87d0.png)

![请添加图片描述](https://img-blog.csdnimg.cn/947b364cc05c4810a880384445d166b9.png)

![请添加图片描述](https://img-blog.csdnimg.cn/938d24c7800342929a5c02c8172bca01.png)


#### Method 2
(Primary Key#, Foreign Key*, Attribute, ....., .....)


## 9. Relationship of higher degree
The degree of relationship can be defined as the number of occurrences in one entity that is associated with the number of occurrences in another entity. 

There is the three degree of relationship:

One-to-one (1:1)
One-to-many (1:M)
Many-to-many (M:N)

1. One-to-one

In a one-to-one relationship, one occurrence of an entity relates to only one occurrence in another entity.
A one-to-one relationship rarely exists in practice.
For example: if an employee is allocated a company car then that car can only be driven by that employee.
Therefore, employee and company car have a one-to-one relationship.


2. One-to-many

In a one-to-many relationship, one occurrence in an entity relates to many occurrences in another entity.
For example: An employee works in one department, but a department has many employees.
Therefore, department and employee have a one-to-many relationship.


3. Many-to-many

In a many-to-many relationship, many occurrences in an entity relate to many occurrences in another entity.
Same as a one-to-one relationship, the many-to-many relationship rarely exists in practice.
For example: At the same time, an employee can work on several projects, and a project has a team of many employees.
Therefore, employee and project have a many-to-many relationship.


-----
# Lecture 3: SQL
Some of The Most Important SQL Commands
•	SELECT - extracts data from a database
•	UPDATE - updates data in a database
•	DELETE - deletes data from a database
•	INSERT INTO - inserts new data into a database
•	CREATE DATABASE - creates a new database
•	ALTER DATABASE - modifies a database
•	CREATE TABLE - creates a new table
•	ALTER TABLE - modifies a table
•	DROP TABLE - deletes a table
•	CREATE INDEX - creates an index (search key)
•	DROP INDEX - deletes an index
![请添加图片描述](https://img-blog.csdnimg.cn/8be57ae3990d4c118d33ea85bda0ea1c.png)
![请添加图片描述](https://img-blog.csdnimg.cn/a73eb34334bd417284079a532421b4c3.png)
![请添加图片描述](https://img-blog.csdnimg.cn/8cd7542fec3f442a89784932f88971a1.png)
## Examples
`More than one attribute has the same name, therefore, you need to specify the name with '.'  `

You don't have to use UNION????
```sql
SELECT DISTINCT Customer.cname, city
FROM Customer, Borrow
WHERE bname = 'Sai Kong' 
AND Borrow.cname = Customer.cname;
```

You can see that you don't have to join anything when you need to select two things, since they can be linked.

![请添加图片描述](https://img-blog.csdnimg.cn/24d6d1b8355046e4a14e899dc55d8a82.png)

![请添加图片描述](https://img-blog.csdnimg.cn/b855c512ecbb4c79afb196a004f4c573.png)



## SELECT `DATA (from bottom to top) SELECT IS THE COLUMN RESULT`


```sql
SELECT column1, column2, ... -- the columns only exist in the output
FROM table_name;

SELECT CustomerName, City 
FROM Customers;

SELECT * 
FROM Customers;
```

### 1. DISTINCT

In a table, there may be a chance to exist a **duplicate value** and sometimes we want to retrieve only **unique values**. In such scenarios, SQL SELECT DISTINCT statement is used.

```sql
SELECT DISTINCT column1, column2, ...
FROM table_name;

SELECT DISTINCT home_town  
FROM students  
```

### 2. AND/OR/NOT
```sql
SELECT column1, column2, ...
FROM table_name
WHERE condition;

SELECT column1, column2, ...
FROM table_name
WHERE condition1 AND condition2 AND condition3 ...; #CAN BE ,

SELECT * FROM Customers
WHERE Country='Germany' AND City='Berlin';
```
```sql
SELECT column1, column2, ...
FROM table_name
WHERE condition1 OR condition2 OR condition3 ...;

SELECT * FROM Customers
WHERE City='Berlin' OR City='München';
```
```sql
SELECT column1, column2, ...
FROM table_name
WHERE NOT condition;

SELECT * FROM Customers
WHERE Country='Germany' AND (City='Berlin' OR City='München');
```

### 3. ORDER BY
```sql
SELECT column1, column2, ...
FROM table_name
ORDER BY column1, column2, ... ASC|DESC;
```
 
### 4. IS NULL/ IS NOT NULL
```sql
SELECT column_names
FROM table_name
WHERE column_name IS NULL;

SELECT column_names
FROM table_name
WHERE column_name IS NOT NULL;
```

### 5. TOP
```sql
SELECT TOP number|percent column_name(s)
FROM table_name
WHERE condition;

SELECT TOP 3 * FROM Customers;
SELECT TOP 50 PERCENT * FROM Customers;
```

### 6. MIN MAX
```sql
SELECT MIN|MAX(column_name)
FROM table_name
WHERE condition;
```

```sql
SELECT MIN(Price) AS SmallestPrice
FROM Products;
```

```sql
SELECT MAX(Price) AS LargestPrice
FROM Products;
```


### 7. COUNT/AVG/SUM
```sql
SELECT COUNT|AVG|SUM (column_name)
FROM table_name
WHERE condition;
```

### 8. LIKE
```sql
SELECT column1, column2, ...
FROM table_name
WHERE columnN LIKE pattern;

LIKE Operator	Description
WHERE CustomerName LIKE 'a%'	Finds any values that start with "a"
WHERE CustomerName LIKE '%a'	Finds any values that end with "a"
WHERE CustomerName LIKE '%or%'	Finds any values that have "or" in any position
WHERE CustomerName LIKE '_r%'	Finds any values that have "r" in the second position
WHERE CustomerName LIKE 'a_%'	Finds any values that start with "a" and are at least 2 characters in length
WHERE CustomerName LIKE 'a__%'	Finds any values that start with "a" and are at least 3 characters in length
WHERE ContactName LIKE 'a%o'	Finds any values that start with "a" and ends with "o"

Symbol	Description	Example
*	Represents zero or more characters	bl* finds bl, black, blue, and blob
?	Represents a single character	h?t finds hot, hat, and hit
[]	Represents any single character within the brackets	h[oa]t finds hot and hat, but not hit
!	Represents any character not in the brackets	h[!oa]t finds hit, but not hot and hat
-	Represents any single character within the specified range	c[a-b]t finds cat and cbt
'#'	Represents any single numeric character	2#5 finds 205, 215, 225, 235, 245, 255, 265, 275, 285, and 295

```

### 9. IN
```sql
SELECT column_name(s)
FROM table_name
WHERE column_name IN (value1, value2, ...);
#or
SELECT column_name(s)
FROM table_name
WHERE column_name IN (SELECT STATEMENT);
```

### 10. BETWEEN..AND/ NOT BETWEEN..AND
```sql 
SELECT column_name(s)
FROM table_name
WHERE column_name BETWEEN value1 AND value2;

SELECT * FROM Products
WHERE Price NOT BETWEEN 10 AND 20;

SELECT * FROM Products
WHERE Price BETWEEN 10 AND 20
AND CategoryID NOT IN (1,2,3);

SELECT * FROM Products
WHERE ProductName BETWEEN 'Carnarvon Tigers' AND 'Mozzarella di Giovanni'
ORDER BY ProductName;
```

### 11. AS
```sql
Table 

SELECT column_name AS alias_name
FROM table_name;

Column 

SELECT column_name(s)
FROM table_name AS alias_name;

SELECT CustomerID AS ID, CustomerName AS Customer
FROM Customers;

SELECT CustomerName AS Customer, ContactName AS [Contact Person] #contain space need []
FROM Customers;

SELECT CustomerName, Address + ', ' + PostalCode + ' ' + City + ', ' + Country AS Address
FROM Customers;
```

### 12. ALL and ANY

ALL means that the condition will be true only if the operation is true for all values in the range. 

is used with `SELECT, WHERE and HAVING` statements

```sql
SELECT column_name(s) FROM table1
UNION|ALL
SELECT column_name(s) FROM table2;
```

The following SQL statement lists the ProductName if ALL the records in the OrderDetails table has Quantity equal to 10. This will of course return FALSE because the Quantity column has many different values (not only the value of 10):

```sql
SELECT ProductName
FROM Products
WHERE ProductID = ALL
  (SELECT ProductID
  FROM OrderDetails
  WHERE Quantity = 10);
```



ANY means that the condition will be true if the operation is true for any of the values in the range.


The following SQL statement lists the ProductName if it finds ANY records in the OrderDetails table has Quantity larger than 99 (this will return TRUE because the Quantity column has some values larger than 99):

```sql
SELECT ProductName
FROM Products
WHERE ProductID = ANY
  (SELECT ProductID
  FROM OrderDetails
  WHERE Quantity = 10);
```



## AGGREGATE

### 13. GROUP BY 
The GROUP BY statement groups rows that have the same values into summary rows, like "find the number of customers in each country".
The GROUP BY statement is often used with aggregate functions (COUNT(), MAX(), MIN(), SUM(), AVG()) to group the result-set by one or more columns.

Group by statement is used to group the rows that have the same value. Whereas Order by statement sort the result-set either in ascending or in descending order. ... In select statement, it is always used before the order by keyword. 

```sql
SELECT column_name(s)
FROM table_name
WHERE condition
GROUP BY column_name(s)
ORDER BY column_name(s);

SELECT COUNT(CustomerID), Country
FROM Customers
GROUP BY Country
ORDER BY COUNT(CustomerID) DESC;
```

```sql
-- MostRentBook: Correct
SELECT bookName, ISBN, author, bookCategory, SUM(bookRentNum)
FROM BOOK
GROUP BY bookName, ISBN, author, bookCategory
HAVING SUM(bookRentNum) >= 
ALL(SELECT SUM(bookRentNum) 
FROM book 
GROUP BY ISBN);
```

```sql
SELECT bookName, ISBN, author, bookCategory, SUM(bookRentNum) 
FROM book 
GROUP BY bookName, ISBN, author, bookCategory, ISBN 
HAVING (SUM(bookRentNum) >= 
ALL(SELECT SUM(B.bookRentNum) 
FROM book B 
GROUP BY B.ISBN));


-- MostRentBook: Wrong
-- SELECT A.bookName, A.ISBN, A.author, A.bookCategory, SUM(A.bookRentNum)
-- FROM book A
-- GROUP BY A.ISBN
-- HAVING SUM(A.bookRentNum) >= ALL(SELECT SUM(B.bookRentNum) FROM book B GROUP BY B.ISBN)
```


### 14. HAVING (with aggregate functions only)
The HAVING clause was added to SQL because the `WHERE keyword cannot be used with aggregate functions`. 
An aggregate function in SQL performs a calculation on multiple values and returns a single value. SQL provides many aggregate functions that include avg, count, sum, min, max, etc.

```sql
SELECT column_name(s)
FROM table_name
WHERE condition
GROUP BY column_name(s)
HAVING condition
ORDER BY column_name(s);

SELECT COUNT(CustomerID), Country
FROM Customers
GROUP BY Country
HAVING COUNT(CustomerID) > 5;
```


15. ANY
The ANY and ALL operators allow you to perform a comparison between a single column value and a range of other values.
The ALL operator:
•	returns a boolean value as a result
•	returns TRUE if ALL of the subquery values meet the condition
•	is used with SELECT, WHERE and HAVING statements
ALL means that the condition will be true only if the operation is true for all values in the range. 

```sql
SELECT column_name(s)
FROM table_name
WHERE column_name operator ANY
  (SELECT column_name
  FROM table_name
  WHERE condition);
```

The following SQL statement lists the ProductName if it finds ANY records in the OrderDetails table has Quantity equal to 10 (this will return TRUE because the Quantity column has some values of 10):
```sql
SELECT ProductName
FROM Products
WHERE ProductID = ANY
  (SELECT ProductID
  FROM OrderDetails
  WHERE Quantity = 10);
```

The following SQL statement lists the ProductName if ALL the records in the OrderDetails table has Quantity equal to 10. This will of course return FALSE because the Quantity column has many different values (not only the value of 10):
```sql
SELECT ProductName
FROM Products
WHERE ProductID = ALL
  (SELECT ProductID
  FROM OrderDetails
  WHERE Quantity = 10);
```

## JOIN

You can use **NATURAL LEFT JOIN** or **LEFT JOIN ON** to solve this problem. The difference between them is that NATURAL LEFT JOIN will automatically match the common columns between two tables, while LEFT JOIN ON requires you to specify the common columns.


```sql
-- Correct: 
SELECT Person.FirstName, Person.LastName, Address.City, Address.State 
FROM Person NATURAL LEFT JOIN Address;
```
```sql
SELECT firstName, lastName, city, state
FROM Person p LEFT JOIN Address a
ON p.personId = a.personId;
```

## UNION

The UNION operator is used to combine the result-set of two or more SELECT statements.

Every SELECT statement within UNION must have the same number of columns
The columns must also have similar data types
The columns in every SELECT statement must also be in the same order


```sql
SELECT employee_id
FROM Employees
WHERE employee_id NOT IN (SELECT employee_id
                          FROM Salaries)
UNION
SELECT employee_id
FROM Salaries
WHERE employee_id NOT IN (SELECT employee_id
                          FROM Employees)
ORDER BY employee_id;
```


## INSERT INTO `DATA (from top to bottom)`

```sql
INSERT INTO table_name (column1, column2, column3, ...)
VALUES (value1, value2, value3, ...);

UPDATE
UPDATE table_name
SET column1 = value1, column2 = value2, ...
WHERE condition;

***WARNING ALL DATA WOULD BE UPDATED AS Juan
UPDATE Customers
SET ContactName='Juan';

DELETE
1.
DELETE FROM table_name 
WHERE condition;
2.
DELETE FROM table_name;


-TABLE 
•	(INNER) JOIN: Returns records that have matching values in both tables
•	LEFT (OUTER) JOIN: Returns all records from the left table, and the matched records from the right table
•	RIGHT (OUTER) JOIN: Returns all records from the right table, and the matched records from the left table
•	FULL (OUTER) JOIN: Returns all records when there is a match in either left or right table


 

INNER\RIGHT\LEFT JOIN

SELECT column_name(s)
FROM table1
INNER JOIN table2
ON table1.column_name = table2.column_name;

SELECT Orders.OrderID, Customers.CustomerName, Orders.OrderDate
FROM Orders
INNER JOIN Customers ON Orders.CustomerID=Customers.CustomerID;

SELECT Orders.OrderID, Customers.CustomerName, Shippers.ShipperName
FROM ((Orders
INNER JOIN Customers ON Orders.CustomerID = Customers.CustomerID)
INNER JOIN Shippers ON Orders.ShipperID = Shippers.ShipperID);

FULL JOIN

SELECT column_name(s)
FROM table1
FULL OUTER JOIN table2
ON table1.column_name = table2.column_name
WHERE condition;

SELECT Customers.CustomerName, Orders.OrderID
FROM Customers
FULL OUTER JOIN Orders ON Customers.CustomerID=Orders.CustomerID
ORDER BY Customers.CustomerName;

SELECT

SELECT *
INTO newtable [IN externaldb]
FROM oldtable
WHERE condition;

INSERT INTO 

INSERT INTO table2
SELECT * FROM table1
WHERE condition;


INSERT INTO Customers (CustomerName, City, Country)
SELECT SupplierName, City, Country FROM Suppliers;

CREATE 
CREATE TABLE table_name (
    column1 datatype,
    column2 datatype,
    column3 datatype,
   ....
);

CREATE TABLE Persons (
    PersonID int,
    LastName varchar(255),
    FirstName varchar(255),
    Address varchar(255),
    City varchar(255) 
);

 

CREATE TABLE Persons (
    ID int NOT NULL,
    LastName varchar(255) NOT NULL,
    FirstName varchar(255) NOT NULL,
    Age int
);

CREATE TABLE Persons (
    ID int NOT NULL UNIQUE,
    LastName varchar(255) NOT NULL,
    FirstName varchar(255),
    Age int
);

CREATE TABLE Persons (
    ID int NOT NULL PRIMARY KEY,
    LastName varchar(255) NOT NULL,
    FirstName varchar(255),
    Age int
);

DROP
DROP TABLE table_name;

ALTER TABLE – ADD/DROP Column
ALTER TABLE table_name
ADD column_name datatype;

ALTER TABLE Customers
ADD Email varchar(255);

ALTER TABLE table_name
DROP COLUMN column_name;

ALTER TABLE Customers
DROP COLUMN Email;

ALTER TABLE Persons
MODIFY Age int NOT NULL;

-DATABASE

CREATE DATABASE databasename;

DROP DATABASE databasename;

BACKUP DATABASE databasename
TO DISK = 'filepath';

CASE
SELECT OrderID, Quantity,
CASE
    WHEN Quantity > 30 THEN 'The quantity is greater than 30'
    WHEN Quantity = 30 THEN 'The quantity is 30'
    ELSE 'The quantity is under 30'
END AS QuantityText
FROM OrderDetails;

 

COMMENTS
--SELECT * FROM Customers;
SELECT * FROM Products;
Multi-line comments start with /* and end with */.
Any text between /* and */ will be ignored.
The following example uses a multi-line comment as an explanation:
/*Select all the columns
of all the records
in the Customers table:*/
SELECT * FROM Customers;
```

## Lab Java

```sql
javac -cp ojdbc8.jar simpleApplication.java
java -cp ojdbc8.jar:. simpleApplication
Enter your username: "20060241d"
Enter your password: iyrhpast
```


## 2/11 Discussion

Memory consumption 100, 1000

The database will process the data faster than the processing side

TO_DATE 

Can't update sql without modify 


# Lecture 4: RELATIONAL MODEL CONCEPT
Relational model can represent as a table with columns and rows. Each row is known as a `tuple`. Each table of the column has a `name or attribute`.

`Domain`: It contains a set of atomic values that an attribute can take.

`Attribute`: It contains the name of a column in a particular table. Each attribute Ai must have a domain, dom(Ai)

`Relational instance`: In the relational database system, the relational instance is represented by a finite set of tuples. Relation instances do not have duplicate tuples.

`Relational schema`: A relational schema contains the name of the relation and name of all columns or attributes.

`Relational key`: In the relational key, each row has one or more attributes. It can identify the row in the relation uniquely.


![请添加图片描述](https://img-blog.csdnimg.cn/7e0fe601c6434480927037796a070cd2.png)

In the given table, NAME, ROLL_NO, PHONE_NO, ADDRESS, and AGE are the attributes.
The instance of schema STUDENT has 5 tuples.
t3 = <Laxman, 33289, 8583287182, Gurugram, 20>



Properties of Relations

Name of the relation is distinct from all other relations.
Each relation cell contains exactly one atomic (single) value
Each attribute contains a distinct name
Attribute domain has no significance
tuple has no duplicate value
Order of tuple can have a different sequence


## 1. Relational Algebra
![在这里插入图片描述](https://img-blog.csdnimg.cn/3799af80e9364a85a2d55e9834ac4455.png)

![请添加图片描述](https://img-blog.csdnimg.cn/9d698bc77adb4581a9ee3f0eabedcdc2.jpeg)

### 1. Select Operation: SIGMA
The select operation selects tuples that satisfy a given predicate.
It is denoted by sigma (σ).
> `Notation:  σ p(r )` 
**WHERE**
where: σ is used for selection prediction
r is used for relation
p is used as a propositional logic formula which may use connectors like: AND OR and NOT. These relational can use as relational operators like =, ≠, ≥, <, >, ≤.

**[Example]**
LOAN Relation  

![请添加图片描述](https://img-blog.csdnimg.cn/4daedf39a42a46d69f9fe6caad159403.png)

> Input: σ BRANCH_NAME="perryride" (LOAN) 
> Output: ![请添加图片描述](https://img-blog.csdnimg.cn/c58b7201d6bf468b8582e469f5171a68.png)


![请添加图片描述](https://img-blog.csdnimg.cn/c2a0af73caff45b49b92eb9cf50b5557.png)




### 2. Project Operation: PI
This operation shows the list of those `attributes` that we wish to appear in the result. Rest of the attributes are eliminated from the table.
It is denoted by ∏.

> `Notation: ∏ A1, A2, An (r )`
**FROM**
Where A1, A2, A3 is used as an attribute name of relation r. 

**[Example]**
CUSTOMER RELATION
![请添加图片描述](https://img-blog.csdnimg.cn/81a48bfcb6144c8f94f5411faaa483a8.png)
> Input: ∏ NAME, CITY (CUSTOMER)  
> Output:
![请添加图片描述](https://img-blog.csdnimg.cn/5218503585d146288222f0366f3ec221.png)

![请添加图片描述](https://img-blog.csdnimg.cn/d34d588e1c8a4451b4cbe7a7caa72096.png)



### 3. Union Operation (or):
Suppose there are two tuples R and S. The union operation contains all the tuples that are either in R or S or both in R & S.
It eliminates the duplicate tuples. It is denoted by ∪.

> Notation: R ∪ S   
A union operation must hold the following condition:
R and S must have the attribute of the same number.
`Duplicate tuples are eliminated automatically`.

**[Example]**
DEPOSITOR RELATION![请添加图片描述](https://img-blog.csdnimg.cn/d9694b1cb0df459eac0140579892e07c.png)
BORROW RELATION![请添加图片描述](https://img-blog.csdnimg.cn/7cb6c292058b41c59c6eece08b761293.png)

> Input:
∏ CUSTOMER_NAME (BORROW) ∪ ∏ CUSTOMER_NAME (DEPOSITOR)  
Output:
![请添加图片描述](https://img-blog.csdnimg.cn/3fca54d9c9f246818dcfcef570e14ca3.png)




### 4. Set Intersection (and):

Suppose there are two tuples R and S. The set intersection operation contains all tuples that are in `both R & S`.
It is denoted by intersection ∩.

> Notation: R ∩ S   

> Input:
∏ CUSTOMER_NAME (BORROW) ∩ ∏ CUSTOMER_NAME (DEPOSITOR)  
Output:

![请添加图片描述](https://img-blog.csdnimg.cn/207ef2ed503b472f8a8889128ff4e105.png)



### 5. Set Difference:
Suppose there are two tuples R and S. The set intersection operation contains all tuples that are `in R but not in S`.
It is denoted by intersection `minus (-)`.

> Notation: R - S  


**[Example]**
Using the above DEPOSITOR table and BORROW table


> Input:
∏ CUSTOMER_NAME (BORROW) - ∏ CUSTOMER_NAME (DEPOSITOR)  
Output:
![请添加图片描述](https://img-blog.csdnimg.cn/2cc2fe3416c948cf9ecd0a764fc18d2b.png)

### 6. Cartesian product |><|
The Cartesian product is used to `combine each row in one table with each row in the other table`. It is also known as a cross product.
It is denoted by X.

> Notation: E X D  

**[Example]**
EMPLOYEE
![请添加图片描述](https://img-blog.csdnimg.cn/8fd4438fd46d46bf88b4de6109fcd64e.png)
DEPARTMENT
![请添加图片描述](https://img-blog.csdnimg.cn/e36c83010dca48e3bf5a61e7dc12fda9.png)

> Input:
EMPLOYEE X DEPARTMENT  
Output:
![请添加图片描述](https://img-blog.csdnimg.cn/13390855aff64439b164bcee8463a1f5.png)


![请添加图片描述](https://img-blog.csdnimg.cn/085494e0362746828e5a399eda4c7b05.png)


## 2. Join Operations:

![在这里插入图片描述](https://img-blog.csdnimg.cn/239a9df431e94fa5a069853376184ae8.png)
![请添加图片描述](https://img-blog.csdnimg.cn/98137e649b234b0e95793efa94c18e7c.jpeg)


![请添加图片描述](https://img-blog.csdnimg.cn/a85b643219de49ada2ec5c76c519c92b.png)



![请添加图片描述](https://img-blog.csdnimg.cn/73ee913b679d468e8530e9d0e2a1b935.png)


A Join operation combines `related tuples from different relations`, if and only if a given join condition is satisfied. It is denoted by ⋈.

EMPLOYEE
![请添加图片描述](https://img-blog.csdnimg.cn/822eb8de989246d58c252fb6892a087f.png)
SALARY
![请添加图片描述](https://img-blog.csdnimg.cn/e5f4ac03981d411a95b2ba17aed2f688.png)

> Operation: (EMPLOYEE ⋈ SALARY)   
![请添加图片描述](https://img-blog.csdnimg.cn/1a9c3322c0ee4af4bfba9f2bc3b591c2.png)

### 1. Natural Join
![请添加图片描述](https://img-blog.csdnimg.cn/9f4af00a74054d48bf8c80c9aec54c00.png)
:

A natural join is the set of tuples of all combinations in R and S that are equal on their common attribute names.
It is denoted by ⋈.
Example: Let's use the above EMPLOYEE table and SALARY table:

> Input:
∏EMP_NAME, SALARY (EMPLOYEE ⋈ SALARY)  
Output:
![请添加图片描述](https://img-blog.csdnimg.cn/564c25cee245422cab34ca5f520760f7.png)


![请添加图片描述](https://img-blog.csdnimg.cn/a8625a11d0d2429286c11a1bc70195fb.png)



### 2. Outer Join:
The outer join operation is an extension of the join operation. It is used to deal with missing information.

Example:
EMPLOYEE
![请添加图片描述](https://img-blog.csdnimg.cn/a932584f0a0a4c209e8eef00394e4eb2.png)
FACT_WORKERS
![请添加图片描述](https://img-blog.csdnimg.cn/afdf89e41244497baed885208b92ccc9.png)

> Input: 
(EMPLOYEE ⋈ FACT_WORKERS)  
Output:
![请添加图片描述](https://img-blog.csdnimg.cn/7b6f8ad28aa64e52b4c26baf837a0969.png)

An outer join is basically of three types:

Left outer join
Right outer join
Full outer join

#### a. Left outer join:

Left outer join contains the set of tuples of all combinations in R and S that are equal on their common attribute names.
In the left outer join, tuples in R have no matching tuples in S.
It is denoted by ⟕.
Example: Using the above EMPLOYEE table and FACT_WORKERS table

> Input:
EMPLOYEE ⟕ FACT_WORKERS   
![请添加图片描述](https://img-blog.csdnimg.cn/41d019c91441419cbe538c234f04e5fb.png)

#### b. Right outer join:
> EMPLOYEE ⟖ FACT_WORKERS  

![请添加图片描述](https://img-blog.csdnimg.cn/879ec4bb7afc4989b7915e2e77308715.png)


#### c. Full outer join:
In full outer join, tuples in R that have no matching tuples in S and tuples in S that have no matching tuples in R in their common attribute name

> EMPLOYEE ⟗ FACT_WORKERS

![请添加图片描述](https://img-blog.csdnimg.cn/7a18c2958fb54477b4594b2cbff2e5a0.png)

### 3. Equi join:
It is also known as an inner join. It is the most common join. It is based on matched data as per the equality condition. The equi join uses the comparison operator(=).

![请添加图片描述](https://img-blog.csdnimg.cn/47ac0a66c8e547a686323f65f63c96e3.png)


> CUSTOMER ⋈ PRODUCT   
![请添加图片描述](https://img-blog.csdnimg.cn/1eaf0a517d174dc9b4d53557b4e88466.png)

## Summary



![请添加图片描述](https://img-blog.csdnimg.cn/3cd9b04c76e64fdbb270d13484161744.png)

PRODUCT: distinct 
EQUIJOIN: LIVES r1, LIVES r2, MANAGES m
NATURAL JOIN: LIVES, MANAGES


THINK FROM THE CONDITION, AND FINALLY FOR THE SELECT 
> SIGMA condition Rel.
> PI cols.... Rel. 
> ![请添加图片描述](https://img-blog.csdnimg.cn/876584e73e164b2bbbba37de2485e04e.png)
> ![请添加图片描述](https://img-blog.csdnimg.cn/2c573f1e79c543c78c03a8362954e0c1.png)
 




![请添加图片描述](https://img-blog.csdnimg.cn/3190596f75d843c183497e7d8cda2828.png)
![请添加图片描述](https://img-blog.csdnimg.cn/df6db5d878274d478e27309169378294.png)

![请添加图片描述](https://img-blog.csdnimg.cn/23ec49a09a334a618a8a3a0a613be5d6.png)

You don't have to = tow tables.attribute anymore!![请添加图片描述](https://img-blog.csdnimg.cn/03cb62ebb2404dadb4d3ebba6dbdfb17.png)

![请添加图片描述](https://img-blog.csdnimg.cn/c88da3e20ba449928194fd3b64ccf0af.png)

![请添加图片描述](https://img-blog.csdnimg.cn/a08532674d6740efa7710463de8db999.png)


![请添加图片描述](https://img-blog.csdnimg.cn/3144cac398e04b02b417532986ecd9bc.png)










---

# Lecture 5: INTEGRITY CONSTRAINTS (ICs) AND NORMAL FORMS
Integrity constraints are a set of rules. It is used to maintain the quality of information.
Integrity constraints ensure that the data insertion, updating, and other processes have to be performed in such a way that data integrity is not affected.
Thus, integrity constraint is used to guard against accidental damage to the database.

![在这里插入图片描述](https://img-blog.csdnimg.cn/48a537c6663a48e588c239f9f29b4db8.png)


## 1. Domain Constraint
Domain constraints can be defined as the definition of a `valid set of values for an attribute`.
The `data type of domain` includes string, character, integer, time, date, currency, etc. The value of the attribute must be available in the corresponding domain. It may also prohibit 'null' values of particular attributes. 
![在这里插入图片描述](https://img-blog.csdnimg.cn/a2b05abb9d364e3a81dc44a5cb42bbe6.png)
Number(6,2) -> 6 digits in total; and 2 digits after the decimal points
1234.56

## 2. Entity Integrity Constraint
The entity integrity constraint states that `primary key value can't be null`.
This is because the primary key value is used to identify individual rows in relation and if the primary key has a null value, then we can't identify those rows.
A table can contain a null value other than the primary key field.
![在这里插入图片描述](https://img-blog.csdnimg.cn/1ec7c1fed4ca4a77ad7ac39538a60175.png)

## 3. Referential Integrity Constraint 
A referential integrity constraint is specified `between two tables`.
In the Referential integrity constraints, if a `foreign key in Table 1 refers to the Primary Key of Table 2`, then every value of the `Foreign Key in Table 1 must be null or be available in Table 2`.

![在这里插入图片描述](https://img-blog.csdnimg.cn/6535d794ee1244ff97ccb03090cae8d7.png)
![请添加图片描述](https://img-blog.csdnimg.cn/556a46cb480a4a289645d4a33d76bdb0.jpeg)


## 4. Key Constraint
Keys are the entity set that is used to identify an entity within its entity set uniquely.
An entity set can have multiple keys, but out of which `one key will be the primary key`. A primary key can contain a unique and null value in the relational table.

![在这里插入图片描述](https://img-blog.csdnimg.cn/8ac1da58f4ab4f7ab59c80003ae63fd2.png)


## Functional Dependency and Normal Forms

Functional Dependency (FD) is a particular kind of constraint that is on the set of “legal” relations n Formal definition:

The functional dependency is a relationship that exists between two attributes. It typically exists between the `primary key and non-key attribute` within a table.

`Actually it implies that if you can find the non-key attribute, it may be easier for you to find out the primary key and candidate keys`.

> X   →   Y  
The left side of FD is known as a determinant, the right side of the production is known as a dependent.

Assume we have an employee table with attributes: `Emp_Id, Emp_Name, Emp_Address`.

Here Emp_Id attribute can `uniquely identify` the Emp_Name attribute of employee table because if we know the Emp_Id, we can tell that employee name associated with it. We can say that Emp_Name is functionally dependent on Emp_Id.

Functional dependency can be written as:

> Emp_Id → Emp_Name   


## Types of Functional Dependency 
### 1. Trivial functional dependency

A → B has trivial functional dependency if B is a subset of A.
The following dependencies are also trivial like: A → A, B → B, AB -> A,.....


### 2. Non-trivial functional dependency

A → B has a non-trivial functional dependency if B is not a subset of A.
When A intersection B is NULL, then A → B is called as complete non-trivial.

### Inference Rules for FDs

#### 1. Reflexive Rule (IR1)

In the reflexive rule, if Y is a subset of X, then X determines Y.
`superkey and candidate key`

> If X ⊇ Y then X  →    Y  
Example:
X = {a, b, c, d, e}  
Y = {a, b, c}  


$\alpha$ -> $\beta$ 
The Cohort AND Department -> Credits_Needed
SeatNo/ Name -> ....

![请添加图片描述](https://img-blog.csdnimg.cn/6cc47777870d48a38357e9ff46fe2a51.png)

#### 2. Augmentation Rule (IR2)
`Commonly being ignored, but very important.`
The augmentation is also called as a partial dependency. In augmentation, if X determines Y, then XZ determines YZ for any Z.

> If X    →  Y then XZ   →   YZ    (XZ stands for X U Z)
Example:
For R(ABCD),  if A   →   B then AC  →   BC  


#### 3. Transitive Rule (IR3)
In the transitive rule, if X determines Y and Y determine Z, then X must also determine Z.

> If X   →   Y and Y  →  Z then X  →   Z    


#### 4. Union Rule (IR4)
Union rule says, if X determines Y and X determines Z, then X must also determine Y and Z.

> If X    →  Y and X   →  Z then X  →    YZ     
> Proof:
> 1. X → Y (given)
> 2. X → Z (given)
> 3. X → XY (using IR2 on 1 by augmentation with X. Where XX = X)
> 4. XY → YZ (using IR2 on 2 by augmentation with Y)
> 5. X → YZ (using IR3 on 3 and 4)


#### 5. Decomposition Rule (IR5)
Decomposition rule is also known as project rule. It is the reverse of union rule.

This Rule says, if X determines Y and Z, then X determines Y and X determines Z separately.

> If X   →   YZ then X   →   Y and X  →    Z   
Proof:
> 1. X → YZ (given)
> 2. YZ → Y (using IR1 Rule)
> 3. X → Y (using IR3 on 1 and 2)


#### 6. Pseudo transitive Rule (IR6)
In Pseudo transitive Rule, if X determines Y and YZ determines W, then XZ determines W.

> If X   →   Y and YZ   →   W then XZ   →   W   
Proof:
> 1. X → Y (given)
> 2. WY → Z (given)
> 3. WX → WY (using IR2 on 1 by augmenting with W)
> 4. WX → Z (using IR3 on 3 and 2)

![请添加图片描述](https://img-blog.csdnimg.cn/f895ae2ede38444d89de90f98480cea7.png)

Data modification anomalies can be categorized into three types:

Insertion Anomaly: Insertion Anomaly refers to when one cannot insert a new tuple into a relationship due to lack of data.
Deletion Anomaly: The delete anomaly refers to the situation where the deletion of data results in the unintended loss of some other important data.
Updatation Anomaly: The update anomaly is when an update of a single data value requires multiple rows of data to be updated.

**Repetition, potential consistency, inability to represent, and loss of data**


## Types of Normal Forms:

Normalization works through a series of stages called `Normal forms`. The normal forms apply to individual relations. The relation is said to be in particular normal form if it satisfies constraints.

![请添加图片描述](https://img-blog.csdnimg.cn/c206583555d14ad59979d7ad1d46fd42.png)

![请添加图片描述](https://img-blog.csdnimg.cn/d59e38e7bb264f8a9257104930c94899.png)



Normal Form	Description
### 1NF
> A relation is in 1NF if it contains an `atomic value`. It states that an attribute of a table cannot hold multiple values. It must hold only `single-valued attribute`. 

Relation EMPLOYEE is not in 1NF because of multi-valued attribute EMP_PHONE.
![请添加图片描述](https://img-blog.csdnimg.cn/a1187165b6f04559adf1d043bd3961b6.png)
![请添加图片描述](https://img-blog.csdnimg.cn/a07bcd97f29b4aa2a5126addf457c55b.png)
S# P# -> Qty
S# -> Status, City
City -> Status

, while Status and City is the non-key attribute, which forms partial relationship with the Primary key S#



#### Problems
- Insert Anomalies
Inability to represent certain information:
Eg, cannot enter “Supplier and City” information until Supplier supplies at least one part
- Delete Anomalies
Deleting the “only tuple” for a supplier will destroy all the information about that supplier
- Update Anomalies
“S# and City” could be redundantly represented for each P#, which may cause potential inconsistency when updating a tuple

#### Solution
![请添加图片描述](https://img-blog.csdnimg.cn/4ccfe128e3a14392b0c2d303d6342d87.png)


### 2NF

所有非关键字字段都由关键字段决定
不能部分依赖，就是说当一个表有组合主键时，其他非主键的字段必须完全依赖于主键。


> No non-prime attribute is dependent on the proper subset of any candidate key of table
**[Example]**
for R1, F1 = {I->C, I->D, CD->N}
> I is the only CK for RL, so no partial dependency in R1, hence satisfying 2NF.
> but I->CD-> N is a transitive dependency, so violates 3NF, so R1 is 2NF

![请添加图片描述](https://img-blog.csdnimg.cn/7362bfd7f8ae46379abf5ea249181027.png)
In the given table, non-prime attribute (Non-CK) TEACHER_AGE is dependent on TEACHER_ID which is a proper subset of a candidate key. That's why it violates the rule for 2NF.

![请添加图片描述](https://img-blog.csdnimg.cn/faa373f1b4f74e3c8a2492010b018864.png)
![请添加图片描述](https://img-blog.csdnimg.cn/69800d2b0a5f46ed9a121081e4e585f8.png)
Update Problems: 1000 supplier live in Hong Kong and Hong Kong status. This pair information will be repeated for each of this 1000 supplier.
![请添加图片描述](https://img-blog.csdnimg.cn/290704e13a164e1ea1efb2b550670d8f.png)


### 3NF (Good Design!)
> `Transitive functional dependency` of non-prime (non-CK) attribute on any super key should be removed.
**[Example]**
R(A,B,C,D,E)
F{A->B, BC->E, and ED->A}
CK: ABC, BCD, CDE
R is in the 3NF since all the attributes of R are ONLY key attributes. 

所有非关键字字段都仅由关键字段决定
![请添加图片描述](https://img-blog.csdnimg.cn/daf83bd5551140eb9da2707a4303fdac.png)

Super key in the table above:
{EMP_ID}, {EMP_ID, EMP_NAME}, {EMP_ID, EMP_NAME, EMP_ZIP}....so on  
Candidate key: {EMP_ID}

Non-prime attributes: In the given table, all attributes except EMP_ID (CK) are non-prime.

Here, EMP_STATE & EMP_CITY dependent on `EMP_ZIP` and `EMP_ZIP` dependent on EMP_ID. The non-prime attributes (EMP_STATE, EMP_CITY) `transitively dependent` on super key(EMP_ID). It violates the rule of third normal form. **2NF ONLY**

F{A,B,C,D,E}
A->C
C->DE
A->C->DE


That's why we need to move the EMP_CITY and EMP_STATE to the new <EMPLOYEE_ZIP> table, with `EMP_ZIP as a Primary key`.



![请添加图片描述](https://img-blog.csdnimg.cn/63696c76a9274c0fb28d03c689b08e84.png)


### BCNF	
> A stronger definition of 3NF is known as Boyce Codd's normal form. A relation R is in BCNF if and only if `every determinant (left-hand side of an FD) is a candidate key`.


![请添加图片描述](https://img-blog.csdnimg.cn/92679fea857446de9f4f8729c5de7668.png)

The combination of S#, P#
![请添加图片描述](https://img-blog.csdnimg.cn/54e44ca0c3c04112b129d28f8c6696b6.png)

multiple candidate keys, and 
these candidate keys are composite ones, and 
they overlap on some common attribute


---

# Lecture 6: FILE ORGANIZATIONS AND INDEXING 

## File Organization
Data stored as magnetised areas on magnetic disk surfaces.
The **block size** B is fixed for each system. Typical block sizes range from B=512 bytes to B=4096 bytes.
Whole blocks are transferred between disk and main memory for processing.

Reading or writing a disk block is time consuming because of the seek time **s** and rotational delay (latency) **rd**

Double buffering can be used to speed up the transfer of contiguous disk blocks

---
A file is a sequence of records, where each record is a collection of data values.
Records are stored in **disk blocks**. The blocking factor **bfr** for a file is the (average) number of file records stored in a disk block.
A file can have **fixed-length** records or **variable-length** records.

---
File records can be **unspanned** (no record can span two blocks) -> a file with fixed-length records
or
**spanned** (a record can be stored in more than one block) -> a file with variable-length records

The physical disk blocks that are allocated to hold the records of a file can be **contiguous, linked, or indexed**

---


## 1. Unordered File 
### 1.1 Pile File Method:
It is a quite simple method. 
- To search for a record, a `linear search` through the file records is necessary. This requires reading and searching half the file blocks on the average, and is hence quite expensive. 
- Reading the records in order of a particular field requires sorting the file records.
- In this method, we store the record in a **sequence, i.e., one after another.** 
- In case of updating or deleting of any record, the record will be searched in the memory blocks. When it is found, then it will be marked for deleting, and the new record is inserted.
- Here, the record will be inserted in the order in which they are inserted into tables. New records are inserted at the end of the file. Record insertion is quite efficient. 
 

**[Example]**
Insertion of the new record:
Suppose we have four records R1, R3 and so on upto R9 and R8 in a sequence. Hence, records are nothing but a row in the table. Suppose we want to insert a new record R2 in the sequence, then it will be placed at the end of the file. Here, records are nothing but a row in any table. 


![请添加图片描述](https://img-blog.csdnimg.cn/16efbfe4f6ec4b879b1f9121e9e9f97b.png)



---
## 2. Ordered File (Sequential File Organization)

This method is the easiest method for file organization. In this method, files are stored sequentially. 

### 2.1 Sorted File Method:

In this method, the new record is always inserted at the file's end, and then it will sort the **sequence in ascending or descending order**. Sorting of records is based on any primary key or any other key.

In the case of modification of any record, it will update the record and then sort the file, and lastly, the updated record is placed in the right place.



**Pros of sequential file organization**

It contains a fast and efficient method for the huge amount of data.
In this method, files can be easily stored in cheaper storage mechanism like magnetic tapes.
It is simple in design. 
It requires no much effort to store the data.
This method is used when most of the records have to be accessed like grade calculation of a student, generating the salary slip, etc.
This method is used for report generation or statistical calculations.

**Cons of sequential file organization**

It will waste time as we cannot jump on a particular record that is required but we have to move sequentially which takes our time.
Sorted file method takes more time and space for sorting the records.

**[Example]**
Insertion of the new record:
Suppose there is a preexisting sorted sequence of four records R1, R3 and so on upto R6 and R7. Suppose a new record R2 has to be inserted in the sequence, then it will be inserted at the end of the file, and then it will sort the sequence.
![请添加图片描述](https://img-blog.csdnimg.cn/28370fa0a99944f490419256c9d6bd12.png)

Binary Tree: Each node corresponds to a disk block; if the file has n blocks, the height of the tree will be $log_2n$

![请添加图片描述](https://img-blog.csdnimg.cn/687d99906cdc4eaead4d36409a72e8bb.png)

---

## 3. Heap Files (Unordered)
It is the simplest and most basic type of organization. It works with data blocks. In heap file organization, the records are inserted at the file's end. When the records are inserted, it doesn't require the sorting and ordering of records.

When the data block is full, the new record is stored in some other block. This new data block need not to be the very next data block, but it can select any data block in the memory to store new records. The heap file is also known as an unordered file.



Suppose we have five records R1, R3, R6, R4 and R5 in a heap and suppose we want to insert a new record R2 in a heap. If the data block 3 is full then it will be inserted in any of the database selected by the DBMS, let's say data block 1.


**Pros of Heap file organization**

It is a very good method of file organization for bulk insertion. If there is a large number of data which needs to load into the database at a time, then this method is best suited.
In case of a small database, fetching and retrieving of records is faster than the sequential record.


**Cons of Heap file organization**

This method is inefficient for the large database because it takes time to search or modify the record. If we want to search, update or delete the data in heap file organization, then we need to traverse the data from staring of the file till we get the requested record.
This method is inefficient for large databases. 

If the database is very large then searching, updating or deleting of record will be time-consuming because there is no sorting or ordering of records. In the heap file organization, we need to check all the data until we get the requested record.




---

## 4. Hashed Files
The hash function **h** should distribute the records uniformly among the buckets. Otherwise, search time will increase because many overflow records will exist.


### 4.1 Static External Hashing

Hash File Organization uses the computation of hash function on some fields of the records. The hash function's output determines the location of disk block where the records are to be placed.

One of the file fields is designated to be the **hash key** of the file. // Primary key itself as the address of the data block. That means each row whose address will be the same as a **primary key** stored in the data block.


The record with hash key value K is stored in bucket i, where i=h(K), and h is the hashing function. 

![请添加图片描述](https://img-blog.csdnimg.cn/b04456fd11dc4327bbf14ddadbd59b26.png)
![请添加图片描述](https://img-blog.csdnimg.cn/4d724b0a3ee64dd2b0885add5d036a5d.png)

**Pros**
- Search is very efficient on the hash key. In a huge database structure, it is very inefficient to search all the index values and reach the desired data. Hashing technique is used to calculate the direct location of a data record on the disk **without using index structure**. In this technique, data is stored at the data blocks whose address is generated by using the hashing function. The memory location where these records are stored is known as **data bucket or data blocks**. In this, a hash function can choose any of the column value to generate the address. 
- When a record has to be received using the hash key columns, then the address is generated, and the whole record is retrieved using that address. In the same way, when a new record has to be inserted, then the address is generated using the hash key and record is directly inserted. The same process is applied in the case of delete and update.
- In this method, there is no effort for searching and sorting the entire file. 
- In this method, each record will be stored randomly in the memory.


**Cons**
Fixed number of buckets M is a problem when the number of records in the file grows or shrinks



#### 4.1.1 Collisions problem
Collisions occur when a new record hashes to a bucket that is
already full.
An overflow file is kept for storing such records; 
overflow records that hash to each bucket can be linked together.

There are numerous methods for collision resolution, including the following: Open Addressing or Chaining


##### 4.1.1.1 Opening Addressing: Linear Probing

When a hash function generates an address at which data is already stored, then the next bucket will be allocated to it. This mechanism is called as Linear Probing.

**[Example]**

>try Bucket_id+1, Bucket_id+2, …

suppose R3 is a new address which needs to be inserted, the hash function generates address as 112 for R3. But the generated address is already full. So the system searches next available data bucket, 113 and assigns R3 to it.


![请添加图片描述](https://img-blog.csdnimg.cn/3d7f84546fd84997a096d55f67325cae.png)



##### 4.1.1.2 Opening Addressing: Quadratic Probing
>try Bucket_id+1, Bucket_id+4,…
3 + 4 = 7

![请添加图片描述](https://img-blog.csdnimg.cn/5795150b7c024f20b251f68d3f08f1d5.png)


#### 4.1.2 Overflow chaining/ Overflow handling
 
 When buckets are full, then a new data bucket is allocated for the same hash result and is linked after the previous one. This mechanism is known as Overflow chaining.

For this method, various overflow locations are kept, usually by extending the array with a number of overflow positions.
In addition, a pointer field is added to each record location. 
A collision is resolved by placing the new record in an unused overflow location and setting the pointer of the occupied hash address location to the address of that overflow location.


**[Example]**

Suppose R3 is a new address which needs to be inserted into the table, the hash function generates address as 110 for it. But this bucket is full to store the new data. In this case, a new bucket is inserted at the end of 110 buckets and is linked to it.

![请添加图片描述](https://img-blog.csdnimg.cn/f03ca97372a44e3fa77e5403c72c2c04.png)


![请添加图片描述](https://img-blog.csdnimg.cn/641154b0310a4a63a8689fe5718ffc31.png)

---
### 4.2 Dynamic And Extendible Hashing
The dynamic hashing method is used to overcome the problems of static hashing like bucket overflow. Dynamic and extendible hashing do not require an overflow area.

In this method, data buckets grow or shrink as the records increases or decreases. The directories can be stored on disk, and they expand or shrink dynamically. Directory entries point to the disk blocks that contain the stored records.

This method makes hashing dynamic, i.e., it allows insertion or deletion without resulting in poor performance. 


Both dynamic and extendible hashing use the binary representation of the hash value h(K) in order to access a
directory.

In dynamic hashing the directory is **a binary tree**. In extendible hashing the directory is an array of size $2^d$ where is called the global depth.


![请添加图片描述](https://img-blog.csdnimg.cn/8e698f06c54c4bcfb4be8d3173d58beb.png)

**[Example]**

![请添加图片描述](https://img-blog.csdnimg.cn/b62860d8f91c4f2e971ce8bf6a461f81.png)


Insert key 9 with hash address 10001 into the above structure:
Since key 9 has hash address 10001, it must go into the first bucket. But bucket B1 is full, so it will get split.
The splitting will separate 5, 9 from 6 since last three bits of 5, 9 are 001, so it will go into bucket B1, and the last three bits of 6 are 101, so it will go into bucket B5.
![请添加图片描述](https://img-blog.csdnimg.cn/a05a8a7e676f418bb103fdd9241826bd.png)
![请添加图片描述](https://img-blog.csdnimg.cn/d960b13d98dd40938f5a7bb717d14f94.png)

**Advantages of dynamic hashing**

- In this method, the performance does not decrease as the data grows in the system. It simply increases the size of memory to accommodate the data.
- In this method, memory is well utilized as it grows and shrinks with the data. There will not be any unused memory lying. This method is good for the dynamic database where data grows and shrinks frequently.


**Disadvantages of dynamic hashing**

- In this method, if the data size increases then the bucket size is also increased. These addresses of data will be maintained in the bucket address table. This is because the data address will keep changing as buckets grow and shrink. If there is a huge increase in data, maintaining the bucket address table becomes tedious.
- In this case, the bucket overflow situation will also occur. But it might take little time to reach this situation than static hashing.


---

## 5. Indexing
![请添加图片描述](https://img-blog.csdnimg.cn/00cc6d4bd2134e6b8e7be11be6224ba8.png)


### 5.1 Ordered indices

The indices are usually sorted to make searching faster. The indices which are sorted are known as ordered indices.

**[Example]**

Suppose we have an employee table with thousands of record and each of which is 10 bytes long. If their IDs start with 1, 2, 3....and so on and we have to search student with ID-543.

In the case of a database with no index, we have to search the disk block from starting till it reaches 543. The DBMS will read the record after reading 543*10=5430 bytes.
**In the case of an index**, we will search using indexes and the DBMS will read the record after reading 542*2= 1084 bytes which are very less compared to the previous case.


#### 5.1.1 Single level index/ Sparse indexing/ Primary index (Ordered)

Applicable conditions:
  Primary index: applicable to a data file which is ordered on the key field (corresponding to the primary key of the corresponding relation), upon which the index is built, and it can be either a dense or non-dense index.
Query types supported by each: 
  Primary index: suitable for “one-record-at-a-time” search with a precise condition (such as given an id, find the corresponding employee); it can also be used to support “ordered read” according to the indexed field (eg, primary key). 


是稀疏索引 仅指向每个块的地址
defined on **ordered** file
ordered on **key** field
1 index entry for each block (in data file)
index entry has **key value** for first record in block, i.e., block anchor
total number of entries in index is same as number of disk blocks
These primary keys are unique to each record and contain 1:1 relation between the records.

One form of an index:
a file of entries <field value, ptr to record>, which is ordered by field value. The index is called an **access path** on the field

一个主文件只可以有一个主索引，但可以有很多个辅助索引。
主索引建立在主码上，辅助索引建立在其他属性
主索引可以改变主文件的储存方式，（数据结构），但辅助索引不可以


##### 5.1.1.1 Dense index

**The dense index contains an index record for every search key value in the data file**. It makes searching faster.
In this, the number of records in the index table is same as the number of records in the main table.
It needs more space to store index record itself. The index records have the search key and a pointer to the actual record on the disk.

![请添加图片描述](https://img-blog.csdnimg.cn/998033f022b041ca95aa5f78aa6dbea1.png)

##### 5.1.1.2 Sparse index

In the data file, **index record appears only for a few items**. Each item points to a block.
In this, instead of pointing to each record in the main table, the index points to the records in the main table in a gap.
![请添加图片描述](https://img-blog.csdnimg.cn/ba2a58f363974f199846ac631de80ccc.png)

---

![请添加图片描述](https://img-blog.csdnimg.cn/17ea1f1d9a724b80ac76bc85b20d3feb.png)

`LINEAR SEARCH`
blocking factor (Bfr) = 512/150 =3 records/book
number of file blocks b = 30000/3 = 10000 blocks

V.S. 

`BINARY SEARCH`

index entry size = 9+7 = 16 bytes
index blocking factor Bfr = block size/  index entry size = 512/16 = 32 entries/ block
number of index block b = 30000/32 = 938 blocks

Binary search $log_2b$ 

![请添加图片描述](https://img-blog.csdnimg.cn/f08445e9452d403ab786549dd650921d.png)
![请添加图片描述](https://img-blog.csdnimg.cn/bc4f7d4938094b949b21b39623fa77f5.png)

**Advantages**
In the sparse indexing, as the size of the table grows, the size of mapping also grows. These mappings are usually kept in the primary memory so that address fetch should be faster. Then the secondary memory searches the actual data based on the address got from mapping. 

**Disadvantages**

If the mapping size grows then fetching the address itself becomes slower. In this case, the sparse index will not be efficient. To overcome this problem, secondary indexing is introduced.




#### 5.2.1 Clustering index  (Ordered)
Applicable conditions:
  Clustering index: applicable to a data file which is ordered on a non-key field, upon which the index is built; it is normally a non-dense index. 
Query types supported by each: 
  Clustering index: suitable for a “batch-at-a-time” search with an exact condition (eg, to list all employees of a given dept). 



A clustered index can be defined as an **ordered** data file. Sometimes the index is created on **non-primary key** columns which may not be unique for each record.

In this case, to identify the record faster, we will group two or more columns to get the **unique value** and create index out of them. 
The records which have similar characteristics are grouped, and indexes are created for these group.

![请添加图片描述](https://img-blog.csdnimg.cn/add9ff5bb86a4f9b9baf2d553e8d193a.png)

**[Example]**
suppose a company contains several employees in each department. Suppose we use a clustering index, where all employees which belong to the same Dept_ID are considered within a single cluster, and index pointers point to the cluster as a whole. Here Dept_Id is a non-unique k


![请添加图片描述](https://img-blog.csdnimg.cn/ed88ccace6f34e8daf027b3cf9fc264a.png)

#### 5.3.1 Secondary index (Non-ordered)

Applicable conditions:
  Secondary index: applicable to a non-ordered data file, and the index is built either on a candidate key or a non-key field; it is always a dense index. 
Query types supported by each: 
  Secondary index: suitable for either “ordered read” (if on a candidate key) or “batch-at-a-time” search (if on a non-key field), in both cases the data file is not required to be ordered.



辅助/二级索引
ordered file
2 fields:
1, same data fields as **non ordering** field
2, block pointer (not record pointer)
if 1 entry for each records, --> dense index
field value-block pointer -> blocks of records pointers -> data file

In the sparse indexing, as the size of the table grows, the size of mapping also grows. These mappings are usually kept in the primary memory so that address fetch should be faster. Then the secondary memory searches the actual data based on the address got from mapping. If the mapping size grows then fetching the address itself becomes slower. In this case, **the sparse index will not be efficient**. To overcome this problem, secondary indexing is introduced.



In secondary indexing, to reduce the size of mapping, another level of indexing is introduced. In this method, the huge range for the columns is selected initially so that the mapping size of the first level becomes small. Then each range is further divided into smaller ranges. `The mapping of the first level is stored in the primary memory, so that address fetch is faster. The mapping of the second level and actual data are stored in the secondary memory (hard disk)`.


![请添加图片描述](https://img-blog.csdnimg.cn/1f281c478e7d4f91b8d72566ff9c86ce.png)


![请添加图片描述](https://img-blog.csdnimg.cn/723c78266a1c402ca5f4f22fb89f69e0.png)

![请添加图片描述](https://img-blog.csdnimg.cn/e514527de3004bffa39968cf4053da07.png)


#### 5.4.1 Multi-level index (primary, secondary, clustering)
Because a single-level index is an ordered file, we can level until all entries of the top level fit in one disk block

create a primary index to the index itself ; in this case, the original index file is called the first-level index and the index to the index is called the second-level index n We can repeat the process, creating a third, fourth, ..., top

> A single-level index is an ordered file, we can level until all entries of the top level fit in one disk block create a primary index to the index itself ; in this case, the original index file is called the first-level index and the index to the index is called the second-level index

A multi-level index can be created for any type of first- level index (primary, secondary, clustering) as long as the first-level index consists of more than one disk block
Such a multi-level index is a form of search tree; however, insertion and deletion of new index entries is a severe problem because every level of the index is an ordered file.

![请添加图片描述](https://img-blog.csdnimg.cn/955036fc105045a69d29986228ffda3e.png)

**Pros**
 A multi-level index can be created for any type of first-
level index (primary, secondary, clustering) as long as
the first-level index consists of more than one disk
block

**Cons**

Such a multi-level index is a form of search tree;
however, insertion and deletion of new index entries is
a severe problem because every level of the index is
an ordered file


#### 5.4.2 Using B Trees and B+ Trees as Dynamic Multi-level Indexes

The B+ tree is a balanced binary search tree. It follows a multi-level index format.
B+ tree file organization is the advanced method of an indexed sequential access method. It uses a tree-like structure to store records in File.
It uses the same concept of key-index where the primary key is used to sort the records. For each primary key, the value of the index is generated and mapped with the record.
The B+ tree is similar to a binary search tree (BST), but it can have more than two children. In this method, all the records are stored only at the leaf node. Intermediate nodes act as a pointer to the leaf nodes. They do not contain any records.


Because of the insertion and deletion problem, most multi-level indexes use B tree or B + tree data structures, which leave space in each tree node (disk block) to allow for new index entries
- In B Tree and B+ Tree data structures, each node corresponds to a disk block


和B+树
B tree: 叶子节点处于同一级
B+：索引字段值重复出现
B：索引字段值仅出现一次
插入删除：
insertion into anode that is not full;
if full-> split into 2 nodes (maybe other tree levels)
deletion is efficient if more than half full
deletion-> half full, it will merge with neighbour

1. Root Node
2. Internal Node
3. Leaf Node

RMB to check the <= or >=

> Order of the tree is p = 4: 4 pointers 
leaf order is: 3, means **MAX** three nodes (like boxes), but each node MUST keep between **half-full and completely full**, i.e., two in this case.


![请添加图片描述](https://img-blog.csdnimg.cn/07626a30fc5e4104aaea8f378f50c253.png)


##### Insertion
- An insertion into a node that is not full is quite efficient; **if a node is full** the insertion causes a split into two nodes
- Splitting may propagate to other tree level


**[Example]**
![请添加图片描述](https://img-blog.csdnimg.cn/1eca610309d24edd85fafc694c630f9b.png)




**[Example]**

<img src = 'insertab.png'>
<img src = 'insertc.png'>


![请添加图片描述](https://img-blog.csdnimg.cn/767a634641fc435e9fce567f0421bc1e.png)

##### Delection
- A deletion is quite efficient if a node **does not become less than half full**
- If a deletion causes a node to become less than half full, it must be merged with neighboring nodes, where merge with the **MAX** value in the neighbouring nodes 
- If there is one internal node left, we should delete the **Root Node**



![请添加图片描述](https://img-blog.csdnimg.cn/cf8ba8bc1bff464f9e7c1619c15e9168.png)

![请添加图片描述](https://img-blog.csdnimg.cn/aaaae3bd37b14f22834f6924bdd4d1f8.png)




**Pros of B+ tree file organization**
- In this method, searching becomes very easy as all the records are stored only in the leaf nodes and sorted the sequential linked list. In the B+ tree, the leaf nodes are linked using a link list. Therefore, a B+ tree can support random access as well as sequential access.
- Traversing through the tree structure is easier and faster.
- The size of the B+ tree has no restrictions, so the number of records can increase or decrease and the B+ tree structure can also grow or shrink.
- It is a balanced tree structure, and any insert/update/delete does not affect the performance of tree.

**Cons of B+ tree file organization**
- This method is inefficient for the static method.



**[Example]**

![请添加图片描述](https://img-blog.csdnimg.cn/7f9a385e2f2d4082a3590ee58700f9e0.png)

The above B+ tree shows that:

There is one root node of the tree, i.e., 25.
There is an intermediary layer with nodes. They do not store the actual record. They have only pointers to the leaf node.
The nodes to the left of the root node contain the prior value of the root and nodes to the right contain next value of the root, i.e., 15 and 30 respectively.
There is only one leaf node which has only values, i.e., 10, 12, 17, 20, 24, 27 and 29.
Searching for any record is easier as all the leaf nodes are balanced.
In this method, searching any record can be traversed through the single path and accessed easily.

**[Example]**

Insert 60
![请添加图片描述](https://img-blog.csdnimg.cn/b26e4b628c8c4199987a6aa5884631d6.png)

![请添加图片描述](https://img-blog.csdnimg.cn/ff2e1d9da69e4366bc4dc7acd02c30f4.png)


### Denormalization 
- The goal of normalization is to separate the logically related attributes into tables to minimize redundancy and thereby avoid the update anomalies that cause an extra processing overheard to maintain consistency of the database.
- The goal of denormalization is to improve the performance of frequently occurring queries and transactions. (Typically the designer adds to a table attributes that are needed for answering queries or producing reports so that a join with another table is avoided.)

Tuning:
The process of continuing to revise/adjust the physical database design by monitoring resource utilization as well as internal DBMS processing to reveal “bottlenecks” such as contention for the same data or devices.

Options to tuning indexes
Drop indexes or/and build new indexes
Change a **non-clustered index to a clustered index** (and vice
versa) 
Rebuilding the index

A query with multiple selection conditions that are connected via **OR** may not encourage the query optimizer to use any index. -> Such a query may be split up and expressed as a union of queries, each with a condition on an attribute that causes an index to be used.
Apply the following transformations -> **NOT** condition may be transformed into a positive expression. 
Embedded **SELECT** blocks may be replaced by joins. -> If an equality join is set up between two tables, the range predicate on the joining attribute set up in one table may be repeated for the other table **WHERE** conditions of SQL may be rewritten to utilize the indexes on multiple columns.





---
# Lecture 7: QUERY PROCESSING & QUERY OPTIMIZATION

The process of choosing a suitable execution strategy for processing a query.

**Two internal representations of a query:**
Query Tree 
Query Graph


## 1. Translating SQL Queries into Relational Algebra

## 2. Search Methods for Selection



<img src = 'selectoperation.png'>

### Linear search (brute force)
Retrieve every record in the file;
Test whether its attribute values satisfy the selection condition. 


### Binary search
Condition: the selection condition involves an equality comparison on a
key attribute on which the file is ordered
An example is OP1 if SSN is the ordering attribute for the employee file.

###  Using a primary index or hash key to retrieve a single record
Condition: the selection condition involves an equality comparison on a key attribute with a primary index (or a hash key)
For example, SSN = 123456789 in OP1, we can use the primary index (or the hash key) to retrieve the record.


### Using a primary index to retrieve multiple records
Condition: the comparison condition is >, ≥, <, or ≤ on a **key field** with a primary index
For example, dnumber > 5 in op2, we use the index to find the record satisfying the corresponding equality condition (dnumber = 5); then retrieve all subsequent records in the (ordered) file. For the condition dnumber < 5, retrieve all the preceding records.

### Using a clustering index to retrieve multiple records
Condition: the selection condition involves an equality comparison on **a nonkey attribute** with a clustering index
for example, dno = 5 in op3, we use the clustering index to retrieve all the records satisfying the selection condition.



## 3. Calculation

1Let relations r1(A, B, C) and r2(C, D, E) have the following properties: r1 has 20,000 tuples, r2 has 45,000 tuples, 25 tuples of r1 fit on one block, and 30 tuples of r2 fit on one block. Estimate the number of block transfers and seeks required, using each of the following join strategies for r1 |X| r2:

r1 needs 800 blocks, and r2 needs 1500 blocks. Let us assume M pages of memory. If M > 800, the join can easily be done in 1500 + 800 disk accesses, using even plain nested-loop join. So we consider only the case where M ≤ 800 pages.

### a. Nested-loop join
Using r1 as the outer relation we need 20000 ∗ 1500 + 800 = 30, 000, 800 disk accesses, if r2 is the outer relation we need 45000 ∗ 800+1500 = 36,001,500 disk accesses

### b. Block nested-loop join

If r1 is the outer relation, we need ⌈ 800/ (M-1) ⌉ ∗ 1500 + 800 disk accesses,

if r2 is the outer relation we need ⌈ 1500/ (M-1) ⌉ ∗ 800 + 1500 disk accesses.

### c. Merge join
Assuming that r1 and r2 are not initially sorted on the join key, the total sorting cost inclusive of the output is $Bs = 1500(2⌈log_{M−1}(1500/M)⌉+2) + 800(2⌈log_{M−1}(800/M)⌉ + 2)$ disk accesses. Assuming all tuples with the same value for the join attributes fit in memory, the total cost is Bs + 1500 + 800 disk accesses.

### d. Hash join
Noted that there is overflow and non-overflow of the hash join; we assume there is no overflow. We also need to consider if there is recursive partitioning. 

We assume no overflow occurs. Since r1 is smaller, we use it as the build relation and r2 as the probe relation. If M > 800/M, i.e. no need for recursive partitioning, then the cost is 3(1500+800) = 6900disk accesses, else the cost is $2(1500 + 800 ⌈log_{M−1}(800) − 1⌉ + 1500 + 800$ disk accesses.

---

Let relations R1(A,B,C) and R2(C,D,E) have the following properties:
 R1 has 20,000 tuples, and 25 tuples of R1 fit on one block
 R2 has 45,000 tuples, and 30 tuples of R2 fit on one block

Estimate the number of block accesses required, using each of the following join strategies for R1*R2:
1) Nested (inner-outer) loop [5 marks]
2) Sort-merge join [5 marks]
3) Hash-join [5 marks]


Using nested (inner-outer) loop strategy, for each tuple in R1, we must perform an access for each tuple in R2. This involves 20,000 x 45,000 = 900,000,000 accesses of tuples in R2. So when we include the 20,000 accesses to read R1, a total of 900,000,000 + 20,000 = 900,020,000 accesses are required.


Using sort-merge join strategy, if

(a) the relations are already sorted by the join attributes. In this case we read each block of R1 and R2 only once, therefore 20,000/25 + 45,000/30 = 2,300 accesses are required;
(b) the relations are not yet sorted, then we’ll need to sort the two tables first, so it requires (800*Ln800 + 1500*Ln1500) + (800+1500).
//the 1st parenthesis is for the two tables to sort, and the 2nd parenthesis is for the actual join.


Using hash-join strategy, we need to first read both R1 and R2 in order to assign pointers to hash buckets, which entails reading 800 blocks (for R1) + 1500 blocks (for R2) = 2300 blocks. On the reasonable assumption that the hash buckets fit in main memory, no block accesses are incurred in creating or accessing the buckets. Each tuple is read once (at most) in the final computation of the join, incurring another 2300 blocks accesses. Therefore, totally 4600 blocks access is required.
//Note: although it can be worse than sort-merge join, it does NOT require the relations to be sorted.




---





## 4. Heuristic Algebraic Optimization Algorithm

Find the last names of employees born after 1957 who work on a project named ‘Aquarius’.

SELECT E.Lname
FROM EMPLOYEE E, WORKS_ON W, PROJECT P
WHERE P.Pname=‘Aquarius’ AND P.Pnumber=W.Pno AND E.Essn=W.Ssn
AND E.Bdate > ‘1957-12-31’;

FOLLOW THE SEQUENCE EMPLOYEE, WORKS_ON, PROJECT

= would be the restrictive, you can assume 
![请添加图片描述](https://img-blog.csdnimg.cn/3a6f2b231fc84ac0aeca0491bd677d52.png)

![请添加图片描述](https://img-blog.csdnimg.cn/2dc456e2949843998ea210731bd989b2.png)

1. order
2. filter
3. project 

向上保留 向下删除
上面有什么就保留什么



![请添加图片描述](https://img-blog.csdnimg.cn/f1f9d6c1562b4c739a0584a0160de5e3.jpeg)



---
# Lecture 8: TRANSACTIONS AND CONCURRENCY CONTROL

**Single-User System:**
At most one user can use the system at one time.
**Multiuser System:**
Many users can access the system concurrently (at the same time).
**Concurrency**
Interleaved processing:
Concurrent execution of processes is interleaved in a single CPU.
Parallel processing:
Processes are concurrently executed in multiple CPUs


## 1. Transaction
The transaction is a set of logically related operation. It contains a group of tasks.
A transaction is an action or series of actions. It is performed by a single user to perform operations for accessing the contents of the database.

Read(X): Read operation is used to read the value of X from the database and stores it in a buffer in main memory. 1 2 3
Write(X): Write operation is used to write the value back to the database from the buffer. 1 2 3 4

1. Find the address of the disk block that contains item X
2. Copy that disk block into a buffer in main memory
3. Copy item X form the program variable names X into its correct location in the buffer
4. Store the updated block from the buffer back to disk 


**[Example]**
> 1.  R(X);  
5.  X = X - 500;  
6.  W(X);  

But it may be possible that because of the failure of hardware, software or power, etc. that transaction may fail before finished all the operations in the set.

**To solve this problem, we have two important operations:**
Commit: It is used to save the work done permanently.
Rollback: It is used to undo the work done.

### 1.1 Property of Transaction 

1. Atomicity
- It states that all operations of the transaction take place at once if not, the transaction is aborted.
- There is no midway, i.e., the transaction cannot occur partially. Each transaction is treated as one unit and either run to completion or is not executed at all.

**Atomicity involves the following two operations:**
Abort: If a transaction aborts then all the changes made are not visible.
Commit: If a transaction commits then all the changes made are visible.

**[Example]**

Let's assume that following transaction T consisting of T1 and T2. A consists of Rs 600 and B consists of Rs 300. Transfer Rs 100 from account A to account B. After completion of the transaction, A consists of Rs 500 and B consists of Rs 400.

If the transaction T fails after the completion of transaction T1 but before completion of transaction T2, then the amount will be deducted from A but not added to B. This shows the inconsistent database state. In order to ensure correctness of database state, the transaction must be executed in entirety.

---

2. Consistency
- The integrity constraints are maintained so that the database is consistent before and after the transaction.
- The execution of a transaction will leave a database in either its prior stable state or a new stable state.
- The consistent property of database states that every transaction sees a consistent database instance.
- The transaction is used to transform the database from one consistent state to another consistent state.

**[Example]**
The total amount must be maintained before or after the transaction.
Total before T occurs = 600+300=900  
Total after T occurs= 500+400=900  
Therefore, the database is consistent. In the case when T1 is completed but T2 fails, then inconsistency will occur.

---

3. Isolation
- It shows that the data which is used at the time of execution of a transaction cannot be used by the second transaction **until the first one is completed**.
- In isolation, if the transaction T1 is being executed and using the data item X, then that data item can't be accessed by any other transaction T2 until the transaction T1 ends.
- The concurrency control subsystem of the DBMS enforced the isolation property.

---

4. Durability

- The durability property is used to indicate the performance of the database's consistent state. It states that the transaction made the permanent changes.
- They cannot be lost by the erroneous operation of a faulty transaction or by the system failure. When a transaction is completed, then the database reaches a state known as the consistent state. That consistent state cannot be lost, even in the event of a system's failure.
- The recovery subsystem of the DBMS has the responsibility of Durability property.


---


### 1.2 Transaction Status 

![请添加图片描述](https://img-blog.csdnimg.cn/b47dbc1e23174820b5dac93eed079750.png)

![请添加图片描述](https://img-blog.csdnimg.cn/a4042eb8013849ad81dea018c5045fc9.png)


1. Active state

The active state is the first state of every transaction. In this state, the transaction is being executed.

**[Example]**
Insertion or deletion or updating a record is done here. But all the records are still not saved to the database.

2. Partially committed

In the partially committed state, a transaction executes its final operation, but the data is still not saved to the database.

**[Example]**
In the total mark calculation example, a final display of the total marks step is executed in this state.

3. Committed

**Force writing a log**
Before a transaction reaches its commit point, any portion of the
log that has not been written to the disk yet must now be written to the disk.
This process is called force-writing the log file before committing
a transaction.


A transaction is said to be in a committed state if it executes all its operations successfully. In this state, all the effects are now permanently saved on the database system.

4. Failed state

If any of the checks made by the database recovery system fails, then the transaction is said to be in the failed state.

**[Example]**
In the example of total mark calculation, if the database is not able to fire a query to fetch the marks, then the transaction will fail to execute.

5. Aborted/ Rollback

If any of the checks fail and the transaction has reached a failed state then the database recovery system will make sure that the database is in its previous consistent state. If not then it will **abort or roll back the transaction** to bring the database into a consistent state.

If the transaction fails in the middle of the transaction then before executing the transaction, all the executed transactions are rolled back to its consistent state.

**After aborting the transaction, the database recovery module will select one of the two operations**:
Re-start the transaction
Kill the transaction

---

## 2. Schedule 
1. Serial Schedule 

The serial schedule is a type of schedule where one transaction is executed completely before starting another transaction. In the serial schedule, when the first transaction completes its cycle, then the next transaction is executed.

**[Example]**
Suppose there are two transactions T1 and T2 which have some operations. **If it has no interleaving of operations**, then there are the following two possible outcomes:

READ WRITE, READ WRITE, READ WRITE
![请添加图片描述](https://img-blog.csdnimg.cn/5d0d3c5489b64729a2af70e6c534be7e.png)
![请添加图片描述](https://img-blog.csdnimg.cn/460bf446178f4dda9558867bfe1c4fda.png)
2. Non-serial Schedule

**If interleaving of operations is allowed**, then there will be non-serial schedule.
It contains many possible orders in which the system can execute the individual operations of the transactions.

**[Example]**
In the given figure (c) and (d), Schedule C and Schedule D are the non-serial schedules. It has interleaving of operations.

READ READ, WRITE READ, WRITE WRITE
![请添加图片描述](https://img-blog.csdnimg.cn/2e7f750fa5cd46d6bd3fc7192a5c88f9.png)
![请添加图片描述](https://img-blog.csdnimg.cn/082dab6fad0745399e6e798e6a576cae.png)


3. Serializable Schedule 

**The serializability of schedules is used to find non-serial schedules** that allow the transaction to execute concurrently without interfering with one another.
It identifies which schedules are correct when executions of the transaction have interleaving of their operations.
**A non-serial schedule will be serializable** if its result is equal to the result of its transactions executed serially.

## Example

T1:  w1(x), r1(y), w1(y) 
T2:  r2(x), r2(y), w2(y) 


> A possible schedule for T1 and T2:
w1(x), r2(x), r1(y), w1(y), r2(y), w2(y)
since it follows the original order

Is the following one a schedule?
r1(y), w1(y), r2(x), r2(y), w2(y), w1(x)

Nope, because w1(x) should be the first and now the order is changed.

---
## 3. Schedules Classified on Recoverability 

A transaction may not execute completely due to a software issue, system crash or hardware failure. In that case, the failed transaction has to be **rollback**. But some other transaction may also have used value produced by the failed transaction. So we also have to rollback those transactions.

Cascaded rollback:
- A single failure leads to a series of rollback
- All uncommitted transactions that read an item from a failed transaction must be rolled back.


### 3.1 Non-recoverable schedule
**non-recoverable schedule:** The schedule will be irrecoverable if 
1. Tj reads the updated value of Ti
2. Tj committed before Ti commit.

Write (A), Read (A)
![请添加图片描述](https://img-blog.csdnimg.cn/08cd2f1240e54bf191c33ebeaa204d6d.png)

The above table 1 shows a schedule which has two transactions. T1 reads and writes the value of A and that value is read and written by T2. T2 commits but later on, T1 fails. **Due to the failure, we have to rollback T1**. T2 should also be rollback because it reads the value written by T1, **but T2 can't be rollback because it already committed**.

### 3.2 Recoverable schedule with cascaded rollback
**Recoverable with cascaded rollback:** The schedule will be recoverable with cascaded rollback if 
1. Tj reads the updated value of Ti
2. Commit of Tj is delayed till commit of Ti.

![请添加图片描述](https://img-blog.csdnimg.cn/281fd270b8884af89e63963ba4dc96f8.png)

The above table 2 shows a schedule with two transactions. Transaction T1 reads and writes A, and that value is read and written by transaction T2. But later on, T1 fails. Due to this, we have to rollback T1. T2 should be rollback because T2 has read the value written by T1. **As it has not committed before T1 commits so we can rollback** transaction T2 as well. So it is recoverable with cascaded rollback.

### 3.3 Cascadeless schedule
![请添加图片描述](https://img-blog.csdnimg.cn/3d9ff70274434985b56ad5caaeec1274.png)

The above Table 3 shows a schedule with two transactions. 
1. Transaction T1 reads and write A and commits
2. value is read and written by T2. 

Every transaction **reads only** the items that are written by committed transactions. 
In other words,
- Before Ti reads an item written by Tj 
- Tj is already committed

### 3.4 Strict schedules
A schedule in which a transaction can **neither read nor write** an item X until the last transaction that wrote X has committed

## Example
S: w1(X,5); w2(X,8); a1 (T1 aborts);
• Initially, X=9
• T1 writes a value 5 for X (keeping 9 as “before image”)
• T2 writes a value 8 for X (keeping 5 as “before image”)
• Then T1 aborts

**Cascadeless**
If the system restore according to the “before image” kept in T1, then 9 will be the value for X now, which means, the effect of T2 is lost

-> it does not violate the cascade less since there is no read here, but there is lost update problem

**Strict**
w2 can not happen until T1 commits

![请添加图片描述](https://img-blog.csdnimg.cn/66c6b262c6f14c9eb01961eb7834096d.png)

---



## 4. Schedules Classified on Serializability 
### 4.1 Conflict Serializable Schedule

- A schedule is called **conflict serializability** if after swapping of non-conflicting operations, it can transform into **a serial schedule**.
- The schedule will be a conflict serializable if it is **conflict equivalent** (one can be transformed to another by swapping non-conflicting operations) to a serial schedule.


** conflict equivalent -> a serial schedule -> conflict serialisable 
In short, it means there is no cycle and the -> can interpret others in the precedence graph, shown in Example.**

**The two operations become conflicting if all conditions satisfy:**

1. Both belong to **separate transactions.**
2. They have the same data item.
3. They contain at least one write operation.

**[Example]**

Swapping is possible only if S1 and S2 are logically equal.
             
Here, S1 = S2. That means it is non-conflict.
![请添加图片描述](https://img-blog.csdnimg.cn/ec634f913ffb4680b0f634027479d0a3.png)

Here, S1 ≠ S2. That means it is conflict.

![请添加图片描述](https://img-blog.csdnimg.cn/b93f0ae044fc4c378f90eafac0380d69.png)

### 4.2 Conflict Equivalent

In the conflict equivalent, one can be transformed to another by swapping non-conflicting operations. In the given example, S2 is conflict equivalent to S1 (S1 can be converted to S2 by swapping non-conflicting operations).

**Two schedules are said to be conflict equivalent if and only if:**
- They contain the **same set of the transaction.**
- If each pair of conflict operations are ordered in the same way.

**[Example]**

Schedule S2 is a **serial schedule** because, in this, all operations of T1 are performed before starting any operation of T2. Schedule S1 can be transformed into a serial schedule by swapping non-conflicting operations of S1.

![请添加图片描述](https://img-blog.csdnimg.cn/057fb03785c04b89ad09d5a52187ac01.png)

After swapping of non-conflict operations, the schedule S1 becomes:

Since, S1 is conflict serializable.
![请添加图片描述](https://img-blog.csdnimg.cn/71c7b74e1b864dfb95a59f25dc41bf8b.png)


**Conflict Equivalent**
S1 and S2 are all WRITE READ
![请添加图片描述](https://img-blog.csdnimg.cn/c7e314dabbe54c39939f37bf91203da4.png)



**Not-Conflict Equivalent** 
This one is READ WRITE

READ A 
               READ A
WRITE A
READ B



---

### 4.3 Result equivalent
Two schedules are called result equivalent if they produce the same final state of the database.


---

Being serializable is not the same as being serial
Being serializable implies that the schedule is a correct schedule.
It will leave the database in a consistent state. The interleaving is appropriate and will result in a state as if the transactions were serially executed, yet will achieve efficiency due to concurrent execution.



---

## 5. Test of Serializability 

Write Read
Read  Write
Write Write
**X READ READ**

Create a node Ti → Tj if Ti executes write (Q) before Tj executes read (Q).
Create a node Ti → Tj if Ti executes read (Q) before Tj executes write (Q).
Create a node Ti → Tj if Ti executes write (Q) before Tj executes write (Q).

** 1. READ AND WRITE is a pair so with the same data you can ignore it, which means if the READ AND WRITE appears consecutively, you just use the WRITE to find the conflicting pairs
2. X READ READ **


![请添加图片描述](https://img-blog.csdnimg.cn/e7a0d70cfe0d4c11977f1ec70d15c272.png)



- If a precedence graph contains a single edge Ti → Tj, then all the instructions of Ti are executed before the first instruction of Tj is executed.

|precedence graph for schedule S contains a cycle| precedence graph for schedule S has no cycle|
|--|--|
|S is non-serializable|S is serializable|

### 5.1 Non-serializable schedule
**[Example for Schedule S being non-serializable]**


Read(A): In T1, no subsequent writes to A, so no new edges
Read(B): In T2, no subsequent writes to B, so no new edges
Read(C): In T3, no subsequent writes to C, so no new edges
Write(B): B is subsequently read by T3, so add edge T2 → T3
Write(C): C is subsequently read by T1, so add edge T3 → T1
Write(A): A is subsequently read by T2, so add edge T1 → T2
Write(A): In T2, no subsequent reads to A, so no new edges
Write(C): In T1, no subsequent reads to C, so no new edges
Write(B): In T3, no subsequent reads to B, so no new edges

![请添加图片描述](https://img-blog.csdnimg.cn/03237379931440f5b62a140dae2c8520.png)

![请添加图片描述](https://img-blog.csdnimg.cn/8c2a267d0d40439fadc2d48206c417c3.png)


### 5.2 Serializable schedule
A schedule S is serializable if it is **equivalent** to some serial schedule of the same transactions.

**[Example for Schedule S being serializable]**

Read(A): In T4,no subsequent writes to A, so no new edges
Read(C ): In T4, no subsequent writes to C, so no new edges
Write(A): A is subsequently read by T5, so add edge T4 → T5
Read(B): In T5, no subsequent writes to B, so no new edges
Write(C ): C is subsequently read by T6, so add edge T4 → T6
Write(B): B is subsequently read by T6, so add edge T5 → T6
Write(C ): In T6, no subsequent reads to C, so no new edges
Write(A): In T5, no subsequent reads to A, so no new edges
Write(B): In T6, no subsequent reads to B, so no new edges

![请添加图片描述](https://img-blog.csdnimg.cn/9412de77662a406d8689117593694563.png)

![请添加图片描述](https://img-blog.csdnimg.cn/f633abb87eba45878c1c3c06b9d6516b.png)



---

## Example 

STEP1: Based on the conflicting pair, we can produce the precedence graph

> Write Read
Read  Write
Write Write
**X READ READ**
Create a node Ti → Tj if Ti executes write (Q) before Tj executes read (Q).
Create a node Ti → Tj if Ti executes read (Q) before Tj executes write (Q).
Create a node Ti → Tj if Ti executes write (Q) before Tj executes write (Q). 

> ** 1. READ AND WRITE is a pair so with the same data you can ignore it, which means if the READ AND WRITE appears consecutively, you just use the WRITE to find the conflicting pairs 
> 2. X READ READ **


![请添加图片描述](https://img-blog.csdnimg.cn/6f5d86c33245477ebc9406ed1ba21778.png)

STEP2: we can draw the precedence graph to determine if it is,
** conflict equivalent -> a serial schedule -> conflict serialisable 
In short, it means there is no cycle and the -> can interpret others in the precedence graph, shown in Example.**
![请添加图片描述](https://img-blog.csdnimg.cn/d1b9d3252e3f4db281eabf4984b5d019.png)

STEP3: we can conclude that if we would like to make it serialisable, by changing the order


![请添加图片描述](https://img-blog.csdnimg.cn/cec4ea56ae8f4e44ad50a0cfc7b8aa2c.png)


---

STEP1
![请添加图片描述](https://img-blog.csdnimg.cn/01409cf881694a1ba72d2c7154ab56e6.png)
![请添加图片描述](https://img-blog.csdnimg.cn/533dfc69f13d4ced91d6a43bc5559bab.png)

STEP2
![请添加图片描述](https://img-blog.csdnimg.cn/43ecc6d0d4054b2e84f48ef78a899e2f.png)



Which of the following schedules is (conflict) serializable? For each serializable schedule, determine the equivalent serial schedules.

a) r1(X); r3(X); w1(X); r2(X); w3(X); 
b) r1 (X); r 3 (X); w 3 (X); w 1 (X); r 2 (X); 
c) r3 (X); r2 (X); w 3 (X); r1 (X); w1(X);

---
## NOT YET MENTIONED IN TGE LECTURE
## View Serializability

conflict serializable can be view serializable, view equivalent to a serial schedule.
The view serializable which does not conflict serializable contains blind writes.



## View Equivalent

**Two schedules S1 and S2 are said to be view equivalent if they satisfy the following conditions:**

1. Initial Read

**An initial read of both schedules must be the same**. Suppose two schedule S1 and S2. In schedule S1, if a transaction T1 is reading the data item A, then in S2, transaction T1 should also read A.


![请添加图片描述](https://img-blog.csdnimg.cn/932d794ed7b2439f9ca12702ded0fff6.png)

Above two schedules are view equivalent because Initial read operation in S1 is done by T1 and in S2 it is also done by T1.

2. Updated Read

In schedule S1, if Ti is reading A which is updated by Tj then in S2 also, Ti should read A which is updated by Tj.

![请添加图片描述](https://img-blog.csdnimg.cn/5c577c8ff6ed48c69bb1580758bd3f17.png)

Above **two schedules are not view equal** because, in S1, T3 is reading A updated by T2 and in S2, T3 is reading A updated by T1.


3. Final Write

**A final write must be the same between both the schedules**. In schedule S1, if a transaction T1 updates A at last then in S2, final writes operations should also be done by T1.

![请添加图片描述](https://img-blog.csdnimg.cn/4d6050858a6d47edb61dc2e049fafa77.png)

Above **two schedules is view equal** because Final write operation in S1 is done by T3 and in S2, the final write operation is also done by T3.

**[Example]**

Schedule S:
![请添加图片描述](https://img-blog.csdnimg.cn/c1b008c72edf4b538012d676d618ff9e.png)

With 3 transactions, the total number of possible schedule
> = 3! = 6  
S1 = <T1 T2 T3>  
S2 = <T1 T3 T2>  
S3 = <T2 T3 T1>  
S4 = <T2 T1 T3>  
S5 = <T3 T1 T2>  
S6 = <T3 T2 T1>  

Taking first schedule S1:

![请添加图片描述](https://img-blog.csdnimg.cn/4a90c2387a5a408f883570524ed51350.png)



**Step 1: Initial Read**

The initial read operation in S is done by T1 and in S1, it is also done by T1.

**Step 2: final updation on data items**

In both schedules S and S1, there is no read except the initial read that's why we don't need to check that condition.

**Step 3: Final Write**

The final write operation in S is done by T3 and in S1, it is also done by T3. So, S and S1 are view Equivalent.

The first schedule S1 satisfies all three conditions, so we don't need to check another schedule.

**Hence, view equivalent serial schedule is:**
> T1    →      T2    →    T3  


---


---

## Failure Classification

### 1. Transaction failure

The transaction failure occurs when it fails to execute or when it reaches a point from where it can't go any further. If a few transaction or process is hurt, then this is called as transaction failure.

Reasons for a transaction failure could be:

- Logical errors: If a transaction cannot complete due to some code error or an internal error condition, then the logical error occurs.
- Syntax error: It occurs where the DBMS itself terminates an active transaction because the database system is not able to execute it. For example, The system aborts an active transaction because it violates serializability or because several transactions, in case of deadlock or resource unavailability.

### 2. System Crash

- System failure can occur due to power failure or other hardware or software failure. 

Example: Operating system error.
Fail-stop assumption: In the system crash, non-volatile storage is assumed not to be corrupted.

### 3. Disk Failure

- It occurs where hard-disk drives or storage drives used to fail frequently. It was a common problem in the early days of technology evolution.

- Disk failure occurs due to the formation of bad sectors, disk head crash, and unreachability to the disk or any other failure, which destroy all or part of disk storage.


---

## Log-Based Recovery

- The log is a sequence of records. Log of each transaction is maintained in some stable storage so that if any failure occurs, then it can be recovered from there.
- If any operation is performed on the database, then it will be recorded in the log.
- But the process of storing the logs should be done before the actual transaction is applied in the database.

**[Example]**
Let's assume there is a transaction to modify the City of a student. The following logs are written for this transaction.

When the transaction is initiated, then it writes 'start' log.
> <Tn, Start>  

When the transaction modifies the City from 'Noida' to 'Bangalore', then another log is written to the file.
> <Tn, City, 'Noida', 'Bangalore' >  

When the transaction is finished, then it writes another log to indicate the end of the transaction.
> <Tn, Commit>  


**There are two approaches to modify the database:**

1. Deferred database modification:

The deferred modification technique occurs if the transaction does not modify the database until it has committed.
In this method, all the logs are created and stored in the stable storage, and the database is updated when a transaction commits.

2. Immediate database modification:

The Immediate modification technique occurs if database modification occurs while the transaction is still active.
In this technique, the database is modified immediately after every operation. It follows an actual database modification.




### Recovery using Log records

When the system is crashed, then the system consults the log to find which transactions need to be undone and which need to be redone.

If the log contains the record <Ti, Start> and <Ti, Commit> or <Ti, Commit>, then the Transaction Ti needs to be redone.
If log contains record<Tn, Start> but does not contain the record either <Ti, commit> or <Ti, abort>, then the Transaction Ti needs to be undone.


---

## Checkpoint

- The checkpoint is a type of mechanism where all the previous logs are removed from the system and permanently stored in the storage disk.
- The checkpoint is like a bookmark. While the execution of the transaction, such checkpoints are marked, and the transaction is executed then using the steps of the transaction, the log files will be created.
- When it reaches to the checkpoint, then the transaction will be updated into the database, and till that point, the entire log file will be removed from the file. Then the log file is updated with the new step of transaction till next checkpoint and so on.
- The checkpoint is used to declare a point before which the DBMS was in the consistent state, and all transactions were committed.

### Recovery using Checkpoint

In the following manner, a recovery system recovers the database from this failure:
![请添加图片描述](https://img-blog.csdnimg.cn/7b761f6bb7e54eae8b70c9d64d524e6a.png)

The recovery system reads log files from the end to start. It reads log files from T4 to T1.

Recovery system maintains two lists, **a redo-list, and an undo-list.**

The transaction is put into redo state if the recovery system sees a log with <Tn, Start> and <Tn, Commit> or just <Tn, Commit>. In the redo-list and their previous list, all the transactions are removed and then redone before saving their logs.

**[Example]**
In the log file, transaction T2 and T3 will have <Tn, Start> and <Tn, Commit>. The T1 transaction will have only <Tn, commit> in the log file. That's why the transaction is committed after the checkpoint is crossed. Hence it puts T1, T2 and T3 transaction into redo list.

The transaction is put into undo state if the recovery system sees a log with <Tn, Start> but no commit or abort log found. In the undo-list, all the transactions are undone, and their logs are removed.

**[Example]**
Transaction T4 will have <Tn, Start>. So T4 will be put into undo list since this transaction is not yet complete and failed amid.

---


## Deadlock in DBMS

A deadlock is a condition where **two or more transactions are waiting indefinitely for one another to give up locks**. Deadlock is said to be one of the most feared complications in DBMS as no task ever gets finished and is in waiting state forever.

**[Example]**
In the student table, transaction T1 holds a lock on some rows and needs to update some rows in the grade table. Simultaneously, transaction T2 holds locks on some rows in the grade table and needs to update the rows in the Student table held by Transaction T1.

Now, the main problem arises. Now Transaction T1 is waiting for T2 to release its lock and similarly, transaction T2 is waiting for T1 to release its lock. All activities come to a halt state and remain at a standstill, where they are mutually waiting for each other. **It will remain in a standstill until the DBMS detects the deadlock and aborts one of the transactions.**


![请添加图片描述](https://img-blog.csdnimg.cn/03a5e6a2f5954c14bdf538e7c8330dca.png)


### 1. Deadlock Avoidance

When a database is stuck in a deadlock state, then it is better to avoid the database rather than aborting or restating the database. This is a waste of time and resource.
**Deadlock avoidance mechanism** is used to detect any deadlock situation in advance. 


|larger database|smaller database|
|--|--|
|deadlock prevention|wait for graph|


### 2. Deadlock Detection

In a database, when a transaction waits indefinitely to obtain a lock, then the DBMS should detect whether the transaction is involved in a deadlock or not. The lock manager maintains a Wait for the graph to detect the deadlock cycle in the database.



### 3. Wait for Graph

This is the suitable method for deadlock detection. In this method, a graph is created based on the transaction and their lock. If the created graph has a cycle or closed loop, then there is a deadlock.
The wait for the graph is maintained by the system for every transaction which is waiting for some data held by the others. **The system keeps checking the graph if there is any cycle in the graph.**

When a chain like: Ti waits for Tj, Tj waits for Tk
and Tk waits for Ti, occurs, a cycle is formed! • One of the transactions will be chosen to abort.


The wait for a graph for the above scenario is shown below:

![请添加图片描述](https://img-blog.csdnimg.cn/d525ff107451421f8cb5b72729124458.png)

<img src = 'deadlock detection.png'>

### Deadlock Prevention

Deadlock prevention method is suitable for a large database. If the resources are allocated in such a way that deadlock never occurs, then the deadlock can be prevented.
The Database management system analyzes the operations of the transaction whether they can create a deadlock situation or not. If they do, then the DBMS never allowed that transaction to be executed.


#### 1. Wait-Die scheme
In this scheme, if a transaction requests for a resource which is already held with a conflicting lock by another transaction then the DBMS simply checks the timestamp of both transactions. It allows the older transaction to wait until the resource is available for execution.

**[Example]**
Let's assume there are two transactions Ti and Tj and let TS(T) is a timestamp of any transaction T. If T2 holds a lock by some other transaction and T1 is requesting for resources held by T2 then the following actions are performed by DBMS:

1. Check if TS(Ti) < TS(Tj) - If Ti is the older transaction and Tj has held some resource, then Ti is allowed to wait until the data-item is available for execution. That means if **the older transaction is waiting for a resource which is locked by the younger transaction**, then the older transaction is allowed to wait for resource until it is available.
2. Check if TS(Ti) < TS(Tj) - If Ti is older transaction and has held some resource and if Tj is waiting for it, then **Tj is killed and restarted later with the random delay** but with the same timestamp.


#### 2. Wound wait scheme

|resource held by older transaction| resource held by younger transaction|
|--|--|
|younger transaction is asked to wait until older releases it| forces younger one to kill the transaction and release the resource. After the minute delay, the younger transaction is restarted but with the same timestamp.|

an older transaction requesting an item held by an
younger transaction preempts the younger one by
aborting it

---

# Lecture 9: DBMS CONCURRENCY CONTROL


Concurrency Control is the management procedure that is required for controlling concurrent execution of the operations that take place on a database.

But before knowing about concurrency control, we should know about concurrent execution.

## Concurrent Execution
In a multi-user system, **multiple users can access and use the same database at one time**, which is known as the concurrent execution of the database. It means that the same database is executed simultaneously on a multi-user system by different users.

## Problems with Concurrent Execution
In a database transaction, the two main operations are **READ and WRITE** operations.

### 1. Lost Update Problems (W-W Conflict)

The problem occurs when two different database transactions perform the read/write operations on the same database items **in an interleaved manner** (i.e., concurrent execution) that makes the values of the items incorrect hence making the database inconsistent.

![请添加图片描述](https://img-blog.csdnimg.cn/d497dfd3bf7e49f8ac0f208e7ea69900.png)
![请添加图片描述](https://img-blog.csdnimg.cn/181dbe2b3e6f4d919272f1360ee7a752.png)


### 1. Phantom Read Problem (W-R Conflict)

The phantom read problem occurs when a transaction reads a database item, and then another transaction updates the database item. Then the first transaction reads the database item again, and it finds that the database item has been updated by the second transaction. This is known as the phantom read problem.

Phantoms: New rows being read using the same read
with a condition.
A transaction T1  may read a set of rows from a table,
perhaps based on some condition specified in the SQL
WHERE clause. uNow suppose that a transaction T2 inserts a new row that
also satisfies the WHERE clause condition of T1, into the
table used by T1. uIf T1 is repeated, then T1 will see a phantom – a row that previously did not exist ! !


### 2. Dirty Read/ Temporary Update Problems (W-R Conflict)

The dirty read problem occurs when one transaction updates an item of the database, and somehow the transaction **fails, and before the data gets rollback,** the updated database item is accessed by another transaction. There comes the Read-Write Conflict between both transactions.
![请添加图片描述](https://img-blog.csdnimg.cn/7740ccc52c0e481c92a2e68755d43440.png)

Then at time t4, transaction TY reads account A that will be read as $350.
Then at time t5, transaction TX rollbacks due to server problem, and the value changes back to $300 (as initially).
But the value for account A remains $350 for transaction TY as committed, which is the dirty read and therefore known as the Dirty Read Problem.

**Value in one transaction has been rolled back, while the others have not.**


### 3. Nonrepeatable Read Problem (W-R Conflict)

Also known as Inconsistent Retrievals Problem that occurs when in a transaction, two different values are read for the same database item. 
![请添加图片描述](https://img-blog.csdnimg.cn/9647d83fc6444d8a870c6f689370c49d.png)

Within the same transaction TX, **it reads two different values of account A**, i.e., $ 300 initially, and after updation made by transaction TY, it reads $400.  It is an unrepeatable read and is therefore known as the Unrepeatable read problem.

**[Example]**
A transaction T1 may read a given value from a table. If
another transaction T2 later updates that value and T1
reads that value again, T1 will see a different value. 

Consider that T1 reads the employee salary for Smith.
Next, T2 updates the salary for Smith.  If T1 reads Smith's salary again, then it will see a different value for Smith's salary

The incorrect summary problem: 

![请添加图片描述](https://img-blog.csdnimg.cn/22921ac5583a479bbbdb5a330311d3ca.png)


### Summary 

<img src = 'violation of serializability.png'>


## Concurrency Control Protocols 
Ensure ACID of the database

### 1. Lock Based Concurrency Control Protocol

In this type of protocol, **any transaction cannot read or write data until it acquires an appropriate lock on it**. There are two types of lock:


There are four types of lock protocols available:

<!-- ##### 1. Simplistic lock protocol

It is the **simplest way of locking the data while transaction**. Simplistic lock-based protocols allow all the transactions to get the lock on the data before insert or delete or update on it. It will unlock the data item after completing the transaction.


##### 2. Pre-claiming Lock Protocol

Pre-claiming Lock Protocols **evaluate the transaction to list all the data items on which they need locks.**
Before initiating an execution of the transaction, it requests DBMS for all the lock on all those data items.
If all the locks are granted then this protocol allows the transaction to begin. When the transaction is completed then it releases all the lock.
If all the locks are not granted then this protocol allows the transaction to rolls back and waits until all the locks are granted.

![请添加图片描述](https://img-blog.csdnimg.cn/0cad3c129539405b82815a1b0595b9f4.png) -->

##### 3. Two-phase locking (2PL)

The two-phase locking protocol divides the execution phase of the transaction into three parts.
1. In the first part, when the execution of the transaction starts, it seeks permission for the lock it requires.
2. In the second part, the transaction acquires all the locks. 
3. In the third phase, the transaction cannot demand any new locks. It only releases the acquired locks. The third phase is started as soon as the transaction releases its first lock.

![请添加图片描述](https://img-blog.csdnimg.cn/25ae40702f1f4045b561943b70e3d439.png)

###### 1. Shared lock
It is also known as a **Read-only lock**. In a shared lock, the data item can only read by the transaction. It can be shared between the transactions because when the transaction holds a lock, then it can't update the data on the data item.

###### 2. Exclusive lock
In the exclusive lock, the data item can be both reads as well as written by the transaction. This lock is exclusive, and in this lock, **multiple transactions do not modify the same data simultaneously.**



There are two phases of 2PL, how to check:

**Growing phase**: In the growing phase, a new lock on the data item may be acquired by the transaction, but **none can be released.**

**Shrinking phase**: In the shrinking phase, existing lock held by the transaction may be released, but **no new locks can be acquired.**


**[Example]**

Upgrading of lock (from S(a) to X (a)) is allowed in growing phase.
Downgrading of lock (from X(a) to S(a)) must be done in shrinking phase.

![请添加图片描述](https://img-blog.csdnimg.cn/6d5cc1e5b3d24a2f858536c10c8bf39c.png)

The following way shows how unlocking and locking work with 2-PL.

Transaction T1:
Growing phase: from step 1-3
Shrinking phase: from step 5-7
Lock point: at 3

Transaction T2:
Growing phase: from step 2-6
Shrinking phase: from step 8-9
Lock point: at 6



Two-phase policy generates three locking algorithms
##### (a) Basic
##### (b) Conservative
##### (c) Strict 

Conservative:
u Prevents deadlock by locking all desired data items before the
transaction begins execution.
n Basic:
u Transaction locks data items incrementally.  This may cause
deadlock…
n Strict:
u A more stricter version of Basic algorithm where unlocking is
performed after a transaction terminates (commits or aborts and rolled-back).  This is the most commonly used two-phase locking algorithm.




##### 4. Strict Two-phase locking (Strict-2PL)

The first phase of Strict-2PL is similar to 2PL. In the first phase, after acquiring all the locks, the transaction continues to execute normally.
The only difference between 2PL and strict 2PL is that Strict-2PL **does not release a lock after using it.**
Strict-2PL **waits until the whole transaction** to commit, and then it releases all the locks at a time.
Strict-2PL protocol **does not have shrinking phase of lock release.**

It does not have cascading abort as 2PL does.![请添加图片描述](https://img-blog.csdnimg.cn/1b0ffbe817444c248d23aa5bc1388aba.png)

### 2. Time Stamp Concurrency Control Protocol
The Timestamp Ordering Protocol is used to order the transactions **based on their Timestamps**. The order of transaction is nothing but the ascending order of the transaction creation.

Basic Timestamp ordering protocol works as follows:

1. Check the following condition whenever a transaction Ti issues a Read (X) operation:

If W_TS(X) >TS(Ti) then the operation is rejected.
If W_TS(X) <= TS(Ti) then the operation is executed.
Timestamps of all the data items are updated.

2. Check the following condition whenever a transaction Ti issues a Write(X) operation:

If TS(Ti) < R_TS(X) then the operation is rejected.
If TS(Ti) < W_TS(X) then the operation is rejected and Ti is rolled back otherwise the operation is executed.

Where,

TS(TI) denotes the timestamp of the transaction Ti.

R_TS(X) denotes the Read time-stamp of data-item X.

W_TS(X) denotes the Write time-stamp of data-item X.


**Advantages and Disadvantages of TO protocol:**

TO protocol ensures serializability since the precedence graph is as follows:
![请添加图片描述](https://img-blog.csdnimg.cn/e56cbd99c31f4c42b3fd88e5fd884f4e.png)

TS protocol ensures freedom from deadlock that means no transaction ever waits.
But the schedule may not be recoverable and may not even be cascade- free.



### 3. Validation Based Concurrency Control Protocol

Validation phase is also known as optimistic concurrency control technique. In the validation based protocol, the transaction is executed in the following three phases:

1. **Read phase**: In this phase, the transaction T is read and executed. It is used to read the value of various data items and stores them in temporary local variables. It can perform all the write operations on temporary variables without an update to the actual database.
2. **Validation phase**: In this phase, the temporary variable value will be validated against the actual data to see if it violates the serializability.
3. **Write phase**: If the validation of the transaction is validated, then the temporary results are written to the database or system otherwise the transaction is rolled back.

Here each phase has the following different timestamps:
Start(Ti): It contains the time when Ti started its execution.
Validation (Ti): It contains the time when Ti finishes its read phase and starts its validation phase.
Finish(Ti): It contains the time when Ti finishes its write phase.

This protocol is used to determine the time stamp for the transaction for serialization using the time stamp of the validation phase, as it is the actual phase which determines if the transaction will commit or rollback.
Hence TS(T) = validation(T).
The serializability is determined during the validation process. It can't be decided in advance.
While executing the transaction, it ensures a greater degree of concurrency and also less number of conflicts. Thus it contains transactions which have less number of rollbacks.


<!-- ## Multiple Granularity
Granularity: It is the size of data item allowed to lock.

It can be defined as hierarchically breaking up the database into blocks which can be locked.
The Multiple Granularity protocol **enhances concurrency and reduces lock overhead**.
It maintains the track of what to lock and how to lock.
It makes easy to decide either to lock a data item or to unlock a data item. This type of hierarchy can be graphically represented as a tree.

**[Example]**
Consider a tree which has four levels of nodes.
1. The first level or higher level shows the entire database.
2. The second level represents a node of type area. The higher level database consists of exactly these areas.
3. The area consists of children nodes which are known as files. No file can be present in more than one area.
4. Finally, each file contains child nodes known as records. The file has exactly those records that are its child nodes. No records represent in more than one file.

Hence, the levels of the tree starting from the top level are as follows:
1. Database
2. Area
3. File
4. Record

**[Example]**
![请添加图片描述](https://img-blog.csdnimg.cn/dfd486b852784f8080eb3b556df58683.png)
The highest level shows the entire database. The levels below are file, record, and fields. There are three additional lock modes with multiple granularity:


**Intention Mode Lock**

Intention-shared (IS): It contains explicit locking at a lower level of the tree but **only with shared locks.**
Intention-Exclusive (IX): It contains explicit locking at a lower level **with exclusive or shared locks.**
Shared & Intention-Exclusive (SIX): In this lock, the node is locked in **shared mode**, and some node is locked in **exclusive mode** by the same transaction.
Compatibility Matrix with Intention Lock Modes: The below table describes the compatibility matrix for these **lock modes**:

![请添加图片描述](https://img-blog.csdnimg.cn/68c9a4875cb14590850bbb0a5bbedadc.png)

**It uses the intention lock modes to ensure serializability. It requires that if a transaction attempts to lock a node, then that node must follow these protocols:**

Transaction T1 should follow the lock-compatibility matrix.
Transaction T1 firstly locks the root of the tree. It can lock it in any mode.
If T1 currently has the parent of the node locked in either IX or IS mode, then the transaction T1 will lock a node in S or IS mode only.
If T1 currently has the parent of the node locked in either IX or SIX modes, then the transaction T1 will lock a node in X, SIX, or IX mode only.
If T1 has not previously unlocked any node only, then the Transaction T1 can lock a node.
If T1 currently has none of the children of the node-locked only, then Transaction T1 will unlock a node.

**Observe that in multiple-granularity, the locks are acquired in top-down order, and locks must be released in bottom-up order.**

If transaction T1 reads record Ra9 in file Fa, then transaction T1 needs to lock the database, area A1 and file Fa in IX mode. Finally, it needs to lock Ra2 in S mode.
If transaction T2 modifies record Ra9 in file Fa, then it can do so after locking the database, area A1 and file Fa in IX mode. Finally, it needs to lock the Ra9 in X mode.
If transaction T3 reads all the records in file Fa, then transaction T3 needs to lock the database, and area A in IS mode. At last, it needs to lock Fa in S mode.
If transaction T4 reads the entire database, then T4 needs to lock the database in S mode. -->

---
## Recovery with Concurrent Transaction

Whenever more than one transaction is being executed, then the interleaved of logs occur. During recovery, it would become difficult for the recovery system to backtrack all logs and then start recovering.
To ease this situation, 'checkpoint' concept is used by most DBMS.

Refer to **Transaction Processing Concept**


When the system recovers from crash, it will construct an undo-list and a redo-list. The log records for transactions on the undo list must be processed in reverse order, while those log records for transactions on the redo-list must be processed in a sequential order.

In the undo phase, the system will roll back all transactions in the undo-list by scanning the log backward from the end. When it finds a log record belonging to a transaction in the undo list, it performs the undo operation as if the log record was found during the rollback of a failed transaction found during the rollback of a failed transaction. Normal transaction processing can be resumed after the undo phase of recovery is over.

In the redo phase, the system replays updates of all transactions by scanning the log forward from the last checkpoint. Some transactions in the redo log must continue in the same order in which the operations are written in the log. Redo operations must be idempotent and executing them again and again is equivalent to executing them only once and the entire recovery process should be idempotent. 


When a detection algorithm determines that a deadlock
occurs, the system must recover from the deadlock
Ø The most common solution is to roll back one or
more transactions in order to break the deadlock Ø Three issues need to be addressed:
#### 1. Selecting a victim 

 We should roll back those transactions which will
incur the “minimum cost” 
Many factors may determine the cost of a rollback, including: how long, the amount of data, and the number of operations that must be undone.


#### 2. Rollback

Once we have decided that a particular transaction
must be rolled back, we must determine how far this transaction should be rolled back 
a) The simplest solution is a total rollback:
abort the transaction and then restart it 


#### 3. Starvation

Starvation occurs when a particular transaction
consistently waits, or restarts, and never gets a chance to proceed further.

In a deadlock resolution it is possible that the same
transaction may consistently be selected as victim and rolled-back.



---
# Lecture 10:  DISTRIBUTED DATABASES






---
# Lab 1 Table Definition, Manipulation and Simple Queries

## Link to SQL

```bash
ssh 20060241d@csdoor.comp.polyu.edu.hk

# enter your password (the one that you use to log in to department’s PC)
 
apollo apollo2

source /compsoft/app/oracle/dbms.bashrc

sqlplus


# Your Oracle account is opened as follows
Username: "20060241d"@dbms
Password: iyrhpast

exit
```

## Import .SQL
假如文件名称有空格 应该输入/反斜杠, 比如/Users/haleyk/Desktop/COMP2411\Database\Systems/Lab/LabData.sql

![请添加图片描述](https://img-blog.csdnimg.cn/f2067924a57d4f7ebb548f276bbd654f.jpeg)

```bash
scp -o ProxyJump=20060241d@csdoor.comp.polyu.edu.hk LabData.sql /Users/haleyk/Desktop/COMP2411/Lab/LabData.sql 20060241d@apollo:/home/20060241d

# load the data after entering the SQL*PLUS
SQL*PLUS:20060241d>@LabData.sql
```


## Exercise

`After  each  insert,  update  and  delete  operations  that  would  modify  the  data  in  the database, you are suggested to do a “COMMIT” operation to ensure the changes take effect immediately`

## 1.1 Common Data Types
CHAR (n) n = maximum length of char string
NUMBER (n,d) n = maximum 
e.g., 1234.56:number(6,2)
![请添加图片描述](https://img-blog.csdnimg.cn/9baacd6522504471ae4dab6e3105e610.png)
 of digits d = maximum number of digits right of decimal
DATE The relevant data plus the actual time of day
LONG Up to 65,536 characters (64K) may be stored per field
RAW Raw binary data



## 1.2 NULL values 
To  forbid  NULL  values  in  a  column,  enter  the  NOT  NULL  clause  at  the  end  of  the column information 



## 2.1 Inserting Tuples into Tables
User variables `&` (or called substitution variable) can be used to help reduce the tedium of data insertion. For example, to insert rows into the DEPT table, enter the following command:
![请添加图片描述](https://img-blog.csdnimg.cn/bf0996889c9c4a8ba34f908c443e5618.png)

## 2.2 Altering Tables
You may add a new column or change the length of an existing column by using the ALTER TABLE command with either the ADD or MODIFY parameters. Note that you may not reduce the width of a column if it contains data, nor may you change data type unless the column is empty.

Change the length of column LOC in table DEPT from 15 to 20

![请添加图片描述](https://img-blog.csdnimg.cn/eb08aead0077496eabaed25a5927960f.png)

## 3.1 Select
SELECT   some columns 
FROM some tables 
WHERE   certain conditions are met
AND/OR


---
# Lab 2 Queries, Arithmetic Expressions and Functions

## 1.1 Selecting Rows within a Certain Range 
BETWEEN/ NOT BETWEEN

## 1.2  Selecting Rows That Match a Value in  List 
SQL > SELECT ENAME, JOB, DEPTNO         
FROM EMP
WHERE JOB IN (‘CLERK’, ‘ANALYST’, ‘SALESMAN’);

/NOT IN

## 1.3 Selecting Rows That Match a Character Pattern  
`% The percent character represents any string of zero or more characters    `
Start begins with M/ end with N
SQL > SELECT ENAME, JOB, DEPTNO           
FROM EMP           
WHERE ENAME LIKE ‘M%‘;

/’%N'

`_ The underscore character means a single character position`

## 2.1 Ordering Rows

Ascending order:
```sql
SELECT SAL, JOB, ENAME
FROM EMP
WHERE DEPTNO = 30
ORDER BY SAL;
```

Descending order: 
```sql
SELECT SAL, JOB, ENAME,
FROM EMP
WHERE DEPTNO = 30
ORDER BY SAL DESC;
```

## 2.2 Ordering Rows Using Multiple Columns
CLERKs are in descending salary order, and all the MANAGERs are in descending salary order, etc.

```sql
SELECT JOB, SAL, ENAME
FROM EMP
ORDER BY JOB, SAL DESC;
```

## 2.3 Ordering Rows By Columns With NULL Values 
SELECT ... ORDER BY ...  ASC/DESC NULLS FIRST/LAST;


## 3.1 Arithmetic Expressions 

![请添加图片描述](https://img-blog.csdnimg.cn/0db4ebc7aff74f91805c87e3a079dafe.png)

```sql
SELECT ENAME, SAL, COMM, SAL+COMM
FROM EMP
WHERE JOB = ‘SALESMAN’;
```
```sql
SELECT ENAME, SAL, COMM
FROM EMP
WHERE COMM > 0.25 * SAL;
```
More than one arithmetic expressions can be used:
```sql
SELECT ENAME, SAL, COMM, (SAL+COMM)*12
FROM EMP
WHERE JOB = ‘SALESMAN’;
```

## 3.2  Arithmetic Expressions with ORDER BY
```sql
SELECT ENAME, COMM/SAL, COMM, SAL
FROM EMP
WHERE JOB = ‘SALESMAN’
ORDER BY COMM/SAL DESC;
```

## 3.3 The NULL Function 
The  expression  `SAL+NVL(COMM,  0)`  will  return  a  value  equal  to  `SAL  +  0`  when  the  COMM field is null.

```sql
SELECT ENAME, JOB, SAL, COMM, SAL+NVL(COMM, 0)
FROM EMP
WHERE DEPTNO = 30;
```


## 3.4 Column Labels
Use _ or "" to avoid any blanks
```sql
SELECT ENAME, JOB, SAL SALARY, COMM COMMISSION, 
SAL+NVL(COMM, 0) TOTAL_COMPENSATION
FROM EMP
WHERE DEPTNO = 30;
```
 “TOTAL COMPENSATION” 
 
## 4.1 Arithmetic Functions (ROUND)

![请添加图片描述](https://img-blog.csdnimg.cn/cc1237d050254f72826887cac032b988.png)

Select the results in three separate columns: unrounded, rounded to the nearest dollar, and rounded to the nearest cent.

```sql
SELECT ENAME, SAL, SAL/22, ROUND(SAL/22, 0), ROUND(SAL/22, 2)
FROM EMP
WHERE DEPTNO = 30;
```


```sql
SELECT ENAME, SAL MONTHLY, ROUND(SAL/22,2) DAILY,ROUND(SAL/(22*8),2) HOURLY
FROM EMP
WHERE DEPTNO = 30;
```

TRUNC(SAL/22,2) DAILY 截断


## 5.1 Character String Functions 
![请添加图片描述](https://img-blog.csdnimg.cn/d60de37511f44ba1842ab700aa3a6817.png)

Concatenate the DNAME column to the LOC column separated by a blank space, a dash and another blank space (‘ – ‘)

```sql
SELECT DNAME || ‘ – ‘ || LOC DEPARTMENTS
FROM DEPT;
```
Abbreviate the department name to the first 5 characters of the department name.

```sql
SELECT SUBSTR(DNAME,1,5)
FROM DEPT
```

```sql
SELECT ENAME, UPPER(ENAME), LOWER(ENAME)
FROM EMP
WHERE UPPER(ENAME) = UPPER(‘Ward’);
```

```sql
SELECT DNAME, LENGTH(DNAME)
FROM DEPT;
```

---

# Lab 3 Aggregate Functions, 'Group By' and 'Having' Clauses

In all the examples so far, we have selected values stored in each row of a table (like SAL), or values calculated for each row (like SAL*12).


## 1.1 Selecting Summary Information from One Group 

Find the average salary for clerk
```sql
SELECT AVG(SAL)
FROM EMP
WHERE JOB = 'CLERK';
```

Find the total salary and total commission for salesmen
```sql
SELECT SUM(SAL), SUM(COMM)
FROM EMP
WHERE JOB = ‘SALESMAN’;
```

Find the highest and lowest paid employee salaries and the difference between them.
```sql
SELECT MAX(SAL), MIN(SAL), MAX(SAL) – MIN(SAL)
FROM EMP;
```

## 2.1 Sub-query

In standard SQL, you may NOT have both `aggregates and non-aggregates` in the same SELECT list.  For example, `SELECT ENAME, AVG(SAL) is an error`.  This is because ENAME is an attribute of each `row` selected and AVG(SAL) is an attribute of `all the rows` selected.  So if you want to find the name and salary of the employee (or employees) who receive the maximum salary, you cannot use the above query

Find the name and salary of the employee (or employees) who receive the maximum salary.
```sql
SELECT ENAME, JOB, SAL
FROM EMP
WHERE SAL =
(SELECT MAX(SAL) FROM EMP);
```
## 2.2 DISTINCT
Count the number of different jobs held by employees in department 30
```sql
SELECT COUNT(DISTINCT JOB)
FROM EMP
WHERE DEPTNO = 30
```

## 3.1 SELECTING SUMMARY INFORMATION FROM GROUPS – GROUP BY 

List the department number and average salary of `each department`
`female or male -> cannot be ordered by`


```sql
SELECT DEPTNO, AVG(SAL)
FROM EMP
GROUP BY DEPTNO;
```

Find  each  department’s  average  annual  salary  for  all  its  employees  except  the managers and the president
```sql
SELECT DEPTNO, AVG(SAL)*12
FROM EMP
WHERE JOB NOT IN (‘MANAGER’, ‘PRESIDENT’)
GROUP BY DEPTNO;
```

Issue  the  same  query  as  above  except  list  the  department  name  rather  than  the department number
```sql
SELECT DNAME, JOB, COUNT(*), AVG(SAL)*12
FROM EMP, DEPT
WHERE DEPT.DEPTNO = EMP.DEPTNO
GROUP BY DNAME, JOB
```
`EMP, DEPT got the same DEPTNO
THUS, DEPT.DEPTNO, EMP.DEPTNO are used to diverse them
However, for SALARY.T SALARY.S, it is the same table, but used for more than one times.`


## 3.2 SPECIFYING A SEARCH-CONDITION FOR GROUPS – HAVING 
Search-conditions for individual rows are specified in the `WHERE clause`, for `groups`, you should use `HAVING clause` to do specification. 

List the average annual salary for all job groups having more than 2 employees in
the group.

```sql
SELECT JOB, COUNT(*), AVG(SAL)*12
FROM EMP
GROUP BY JOB
HAVING COUNT(*) > 2;
```
## 3.3  More on Sub-query
List  the  job  groups  that  have  an  average  salary  greater  than  the  average  salary of managers.

```sql
SELECT JOB, AVG(SAL)
FROM EMP
GROUP BY JOB
HAVING AVG(SAL) >
(SELECT AVG(SAL) FROM EMP
WHERE JOB = ‘MANAGER’);
```


## 4.1 4 EFFECTS OF NULL VALUES ON GROUP FUNCTIONS
 Null values do not participate in the computation of group functions. 


```sql 
SELECT SUM(SAL), COUNT(SAL), AVG(SAL), SUM(COMM),
COUNT (COMM), AVG(COMM)
FROM EMP
WHERE DEPTNO = 30;
```
List  the  average  commission  of  employees  who  receive  a commission,  and  the average  commission  of  all  employees  (treating  employees  who  do  not  receive  a commission as receiving a zero commission).

```sql
SELECT AVG(COMM), AVG(NVL(COMM, 0))
FROM EMP
WHERE DEPTNO = 30;
```
## 5 FORMATING QUERY RESULTS INTO A REPORT 
In this section, you will learn some more SQL*Plus commands to improve the appearance (format) of a query result.  The commands to be covered in this section 




---

# PROJECT

A Group Project of Database Systems (COMP2411) subject at The Hong Kong Polytechnic University, made by CHEN Derun, JIANG Guanlin, KWOK Hin Chi, LIU Minghao, YE Haowen, and ZHANG Wengyu, 2022-11-19

[Library Management System Project](https://github.com/HaleyKwok/Library_Management_System_Project)

---

# REFERENCES

Fundamentals-of-Database-Systems-Pearson-2015-Ramez-Elmasri-Shamkant-B.-Navathe.pdf








