
2026-04-19 10:12

Status:

Tags:

# Data modeling Using the Entity-Relationship (ER) Model

##### Author: Ed Hoboken


## References



### Notes

UML diagrams are very useful in Data modeling

## Using High-Level Conceptual Data Models for Database Design

![[Pasted image 20260419101537.png]]

###### So obviously you must have everything figured out and you must know how you want to store the data before you even get to the fun part.

It is useful to specify the functional requirements, which consist of operations (or transactions)

You must also create the conceptual schema for the database. This will be the concise details of all relationships, constraints, and entity types.

You then want to implement the data model using SQL. This step is called logical design or data modeling mapping


The last step is the physical design. AKA how the data will be stored  physically. How much memory do you need? ETC
## Sample Database Application

For a company database, there would be multiple departments, each with managers and employees

A department can be in charge of multiple projects as well, which would all be unique and have their own identifier.


## Entity Types, Entity Sets, Attributes, and Keys


#### Entities and Attributes.

An entity is basically a thing or object in the real world. Each entity then has it's own seperate attributes

###### Some examples would be the Employee entity, the Student entity, the Customer entity. Some attributes would include salary for the employee, classes registered for the student, and orders placed for the customer.


![[Pasted image 20260419102258.png]]

###### So all of the rhombuses are the entities and the circles are attributes

![[Pasted image 20260419102415.png]]


###### SO the two entities here would be the company entity, and then the employee entity, both with their unique attributes.


For a reminder, composite attribues can be divided into smaller parts, while atomic attributes can no longer be split.

###### Some examples would include address for composite, since an address is composed of zip code, street address, city


###### The name would also be a composite attribute as well, since name can be split into first name, middle name, and last name.


![[Pasted image 20260419102630.png]]

#### Single valued versus multivalued attributes


Most attributes have a single value for a particular entity; such attributes are single valued


A multivalued attribute may have lower and upper bounds to constrain the number of values allowed for each individual entity.



#### Stored vs derived values

A derived value can be determined from other inputs

###### An example of this would be age for example. When you enter the date you were born, the system can automatically calculate how old you are.


The birthdate attribute would be the stored value in the database



#### Entity types, Entity sets, Keys, and Value Sets


![[Pasted image 20260419103344.png]]



###### So here the entity type would just be either Employee or Company, and the set would be all of the different people that subscribe to that entity


The entity type defines a schema or intension for a set of entities that share the same structure.

The key of an entity is basically the uniqueness of that specific attribute.


###### For employees, it could be the SSN since that is unique. For the company, it could be the company name for example, But then again there are multiple companies that have the same name and therefore that would not work very well. So maybe adding a company ID would work here.


![[Pasted image 20260419103754.png]]


###### So for the car, the keys would be the registration and the vehicle ID, since both of those will always be unique


#### Value Sets (Domain) of attributes

If the range of ages allowed for employees is between 16 and 70, we can specify the value set of the Age attribute of Employees to be the set of integer numbers between 16 and 70

###### I'm sure we could do something similar for names. We could say that the value set is simply the 26 letters from A to Z, but then again there are weird exceptions like the son of Elon who has a weird character as well as people who have accents in their names so maybe not a good idea.


![[Pasted image 20260419104206.png]]



###### So here the underlined values would be the primary keys. My question is that if every entity needs a primary key, then why does the DEPENDENT relationship not have anything there?


## Relationship Types, Relationship Sets, Roles, and Structural Constraints

As you may have noticed, a lot of the entities that we have seen are related to other entities there.


#### Relationship Types, Sets, and Instances

![[Pasted image 20260419104609.png]]

###### So here we can see that we have employees connected to a works for entity. I mean it makes sense. All employees must have a boss, and they all must be associated to a department as well.

#### Relationship Degree, Role Names, and Recursive Relationship

In the top example, the WORKS_FOR entity would be of degree two, since both the employee entity and the department entity both are connected to it.


![[Pasted image 20260419104827.png]]


#### Constraints on Binary Relationship Types

So to keep the example of WORKS_FOR, EMPLOYEE, AND DEPARTMENT. Each department could be related to max the number of employees at the company, but an employee can only be connected to one department

![[Pasted image 20260419105251.png]]



## Weak Entity Types


a DRIVER_LICENSE entity would be very weak since it cannot exist without a PERSON entity. 


## Refining the ER Design for the Company Database

- MANAGES, which is a 1:1 relationship type between EMPLOYEE and DEPARTMENT. EMPLOYEE participation is partial and DEPARTMENT participation is not clear from the requirements.

###### Is Employee participation partial since an employee might not manage a department or?


- WORKS_FOR a 1:N relationship type between DEPARTMENT and EMPLOYEE

###### This checks out. A boss has many employees, but an employee does not have many bosses.


## ER Diagrams, Naming Conventions, and Design Issues


In naming, we must use nouns appearing in the narrative tend to give rise to entity type names, and the verbs must tend to indicate names of relationship types


![[Pasted image 20260419105858.png]]



## UML Notation

![[Pasted image 20260419105935.png]]



