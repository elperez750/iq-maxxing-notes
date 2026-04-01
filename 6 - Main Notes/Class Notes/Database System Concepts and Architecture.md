

2026-03-31 19:34

Status:

Tags:

# Database System Concepts and Architecture

##### Author: Ed Hoboken


## References

### Notes

## Data Models, Schemas, and Instances

**Data Abstraction** - Generally refers to the suppression of  details of data organization and storage, and the highlighting of the essential features for an improved understanding of data

**Data model** - collection of concepts that  can be used to describe the structure of a database—provides the necessary means  to achieve this abstraction.


### Categories of Data Models

#### High level or conceptual data models provide concepts that are close to the way many users perceive data

#### Low level or physical data models provide concepts that describe the details of how data is stored.


###### So basically the low level is what is stored on the servers, and the high level is what we see?


#### Conceptual models use concepts such as entities, attributes, and relationships.

**Entity** - Represents a real world object or concept, such as an employee or a project

**Attribute** - Represents some property of interest that further describes an entity, such as the employee's name or salary

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
- Support of multiple user views.

### The Three-Schema Architecture

- External Level
- Conceptual Level
- Internal Level
![[Pasted image 20260331212128.png]]


#### The internal level has an internal schema, which describes the physical  storage structure of the database. The internal schema uses a physical data  model and describes the complete details of data storage and access paths for  the database. 

###### Would this just simply be how the data is stored in bits? 


#### The conceptual level has a conceptual schema, which describes the structure  of the whole database for a community of users. The conceptual schema hides  the details of physical storage structures and concentrates on describing entities, data types, relationships, user operations, and constraints. Usually, a representational data model is used to describe the conceptual schema when a  database system is implemented. This implementation conceptual schema is  often based on a conceptual schema design in a high-level data model. 


###### I feel like this is just a regular schema that database engineers design

#### The external or view level includes a number of external schemas or user  views. Each external schema describes the part of the database that a particular user group is interested in and hides the rest of the database from that  user group. As in the previous level, each external schema is typically implemented using a representational data model, possibly based on an external schema design in a high-level conceptual data model

### Data Independence

- Logical data independence -  the capacity to change the conceptual schema without having to change external schemas or application programs.

- Physical data independence -  The capacity to change the internal schema without having to change the conceptual schema.


