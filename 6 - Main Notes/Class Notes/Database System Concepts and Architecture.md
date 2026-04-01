

2026-03-31 19:34

Status:

Tags: [[Software Development]], [[Database Management]]

# Database System Concepts and Architecture

##### Author: Ed Hoboken


## References

### Notes

## Data Models, Schemas, and Instances

**Data Abstraction** - Generally refers to the suppression of  details of data organization and storage, and the highlighting of the essential features for an improved understanding of data

###### So basically only highlighting key features in the schema, like name or id??

#### Clarification: It’s about hiding  _how_ data is stored (files, pages, indexes) and showing only _what_ it means (tables, attributes, relationships)


**Data model** - collection of concepts that  can be used to describe the structure of a database—provides the necessary means  to achieve this abstraction.


#### The **data model** is the _language / toolkit_ (e.g., “relational tables with rows, columns, keys”) you use; a **schema** is one specific design written _in_ that model.

###### How is this different from the schema???

### Categories of Data Models

#### High level or conceptual data models provide concepts that are close to the way many users perceive data

#### Low level or physical data models provide concepts that describe the details of how data is stored.


###### - Clarification: High‑level = how users think about the data (entities, attributes, relationships); low‑level = how the DBMS actually lays it out on disk (records, blocks, indexes).


###### So basically the low level is what is stored on the servers, and the high level is what we see? Yes it is. High level would be thinking of all the schemas and the attributes that an entry should have. Then, we have how it is organized on disk.



#### Conceptual models use concepts such as entities, attributes, and relationships.

**Entity** - Represents a real world object or concept, such as an employee or a project

###### So like a person would be an entity?


**Attribute** - Represents some property of interest that further describes an entity, such as the employee's name or salary

###### So this would be like the persons name or age?


**Relationship** - Represents an association among the entities

###### This might be like the relationship between a teacher and a student, or a employee and the boss


### Schemas, Instances, and Database State

**Database Schema** - The description of a database

#### Example of a schema
![[Pasted image 20260331211743.png]]

###### No matter how many entries are added, this schema will usually stay the same. For example, it is rare for the student to not have a "name" attribute


## Three-Schema Architecture and Data Independence

#### Three of the four important characteristics of the database approach are:

- Use of a catalog to store the database description (Schema)
- Insulation of programs and data

###### This just means keep the data and the application in a separate place right??

- Support of multiple user views.

###### This is essentially just to keep people from not updating a view.


### The Three-Schema Architecture

- External Level

###### Maybe this could be like a form that the user can use to add something, such as a name change.

#### Clarification: The **external schema** is the _logical view_ a user or group sees (often implemented as views); a form is one UI built on top of that view


- Conceptual Level

###### Schema???


#### Clarification: The **conceptual schema** is the _single, integrated model_ of the whole database: all entities, attributes, relationships, and global constraints.


- Internal Level

###### How the data looks like in the database?

#### Clarification: Internal schema = how data is organized physically: record formats, file organization, indexes, page layout, storage devices.



![[Pasted image 20260331212128.png]]


### Internal Level

- The internal level has an internal schema, which describes the physical storage structure of the database. 
- The internal schema uses a physical data model and describes the complete details of data storage and access paths for  the database. 

###### Would this just simply be how the data is stored in bits? 

### Conceptual Level

- The conceptual level has a conceptual schema, which describes the structure  of the whole database for a community of users. 

- The conceptual schema hides  the details of physical storage structures and concentrates on describing entities, data types, relationships, user operations, and constraints. 

- Usually, a representational data model is used to describe the conceptual schema when a  database system is implemented. This implementation conceptual schema is  often based on a conceptual schema design in a high-level data model. 

###### I feel like this is just a regular schema that database engineers design

### External View

- The external or view level includes a number of external schemas or user views. 
- Each external schema describes the part of the database that a particular user group is interested in and hides the rest of the database from that  user group. 
- As in the previous level, each external schema is typically implemented using a representational data model, possibly based on an external schema design in a high-level conceptual data model

###### Yeah so basically a form to input data like I mentioned above.

### Data Independence

- Logical data independence -  the capacity to change the conceptual schema without having to change external schemas or application programs.

###### So basically if we were to add a new field in the database, this should not change anything in our project.


- Physical data independence -  The capacity to change the internal schema without having to change the conceptual schema.

###### So this basically has to do with the physical aspect of the database, meaning that changing the hardware or internal physical schema will not get rid of the data in there.


###### For example reorganizing files on disk would not affect the physical aspect


## Database Languages and Interfaces

### DBMS Languages

- One language is maintained, called the **Data definition language** (DDL)

- Another language is used to specify the internal schema. This is the **Storage definition language**(SDL)

- Another language is used to specify user views and their mappings to the conceptual schema. This is **View definition language**(VDL)

- A language must be put in place to retrive, insert, delete, and modify the data. This is the **Data manipulation language**(DML)

###### So this is basically SQL? I mean this is the language that is used to write queries for the most part.

#### Clarification: In practice, SQL covers DDL + DML, and often view definition and some storage details; the textbook just conceptually separates their roles.



#### Clarification: DDL/SDL/VDL talk about **defining structure**; DML is about **changing/querying data** inside that structure.


### DBMS Interfaces

#### Menu-based interfaces for Web Clients or Browsing

* These interfaces present the user with lists of options (called menus) that lead the user through the formulation of a request. 

###### Essentially, it sounds just like the GUI that is provided with PostgresSQL


#### Apps for Mobile devices

- These interfaces present mobile users with access to  their data.

###### So essentially, this will just have be like a banking app, where users can access their data.


## The Database System Environment

### DBMS Component Modules

- The database and the DBMS catalog are usually stored on disk
- Access to the  disk is controlled primarily by the **operating system (OS)**
- Many DBMSs have their own **buffer management** module to schedule disk read/write, because management of buffer storage has a considerable  effect on performance.
- A **Query compiler** compiles the query into an internal form
- **Query optimizer** is concerned with the rearrangement and possible reordering of operations
- The **Precompiler** extracts DML commands from an application program written in a host programming language.
	

### Database System Utilities

- **Loading** -  loading utility is used to load existing data files—such as text  files or sequential files—into the database
- **Backup** - A backup utility creates a backup copy of the database, usually by  dumping the entire database onto tape or other mass storage medium
- **Database storage reorganization** - Such a utility monitors database usage and provides statistics to the DBA
- **Performance monitoring** - Such a utility monitors database usage and provides statistics to the DBA


### Tools, Application Environments, and Communications Facilities

- **Data dictionary** - This is used to store catalog information about schemas and constraints, as well as sdesign decisions, usage standards, application program descriptions, and user information


## Centralized and Client/Server Architectures for DBMSs

### Centralized DBMSs Architectures
- Older architectures use mainfram computers to provide the amin processing for all system functions, including user application programs and user interface programs
- The reason was that in older systems, most users accessed the DBMS via computer terminals that did not have processing power and only provided display capabilities.  

![[Pasted image 20260401102937.png]]


### Basic Client/ Server Architectures
- **Client/server architecture** - This was developed to deal with computing environments in which a large number of PCs, workstations, file servers, printers, database servers, web servers, email servers also fall into this category

![[Pasted image 20260401103107.png]]


![[Pasted image 20260401103137.png]]



### Two-Tier Client/Server Architectures for DBMSs

- The server is often called a **query server** or **transaction server** because it provides these two functionalities. In an RDBMS, the server is  also often called an SQL server

- A standard called **Open Database Connectivity (ODBC)** provides an **application programming interface (API)**,  which allows client-side programs to call the DBMS, as long as both client and  server machines have the necessary software installed

- The architectures described here are called **two-tier** architectures because the software components are distributed over two systems: client and server.


### Three-Tier and n-Tier Architectures for Web Applications.

- Many Web applications use an architecture called the **three-tier architecture**


![[Pasted image 20260401103921.png]]



## Classification of Database Management Systems


- Data model is a way to classify these systems
- The main data model for most commercial DBMSs is the **relational data model**.
- **object model** is another one but has not gained widespread attention
- 

