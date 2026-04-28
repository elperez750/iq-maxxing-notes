


2026-04-27 11:09

Status:

Tags:

# CS 420 Midterm study guide

##### Author: Elliott Perez


## References



### Notes

## Database fundamentals

Universe of Discourse: The real-world "world of interest" a database models

###### So to me, this would be like a company, a school, a library. These are all real world objects

Roles: DBA vs end user

###### DBA is Database Admin and im guessing that the end user would just simply be the person who is indirectly accessing the database.

Three-schema architecture: External, conceptual, internal; 

###### So external is just what the user would see. The conceptual would be the schema that is implemented by the DBA. The internal would just be how the data is stored in the hardware


DDL vs DML:
- **DDL**: Define/alter schema (CREATE TABLE, ALTER TABLE)
- **DML**: Manipulate data (INSERT, UPDATE, DELETE, SELECT)


###### DDL is how the data will look and how tables will look

###### DML is simply inputting data into the defined schema


## Relational notation and constraints

Relational notation looks like this: $R_{\underline{A},B,C}$

###### So here the term that is underlined would be the primary key, so A is the primary key here.

Primary key vs super key:
- Primary key: Chosen minimal superkey
- Superkey: Any attribute set that uniquely identifies tuples

###### So from my understanding, the superkey is basically all the keys that can be used to uniquely identify a tuple. Theoretically, doesn't this mean that most if not all attributes would be a superkey since they uniquely identify the tuple?

###### So the primary key would just be the minimal amount of attributes to uniquely describe a tuple. Most of the time that is usually one or two attributes

**Candidate Key**: All minimal superkeys; One becomes primary

**Default superkey**: All attributes of the relation.
###### Literally what I said before!!

**Entity integrity**: Primary key attributes cannot be null

###### This makes sense to me. You need something to uniquely identify each entity.

**Referential integrity**: FKs must match PKs in referenced relation.

Insert/delete operations that violate integrity:
- Insert with null or duplicate PK -> entity integrity violation
- Delete a parent row that has children -> referential integrity violation unless handled by CASCADE/SET NULL

###### So for the delete a parent example, that would only be the case if the entity was a weak entity. 


## Normalization and functional dependencies

**1NF**: No repeating groups, atomic values

**2NF**: In 1NF and no partial dependency of non-key attributes on part of a composite key

**3NF**: In 2NF and no transitive dependency of non-key attributes on other non-key attributes


Examples:

Insert examples here


## ER modeling: strong/weak, identifying relationships

Entities: employee, department, dependent, workson, project, deptlocations

###### Some other examples that are not relate but that would be considered entities would be a student, teacher, courses, and grades


A strong entity: Has its own PK 

###### Examples would be an employee, department, project

A weak entity: Depends on another entitie's PK plus its own partial key

###### This would be dependent, which quite literally cannot exist without an employee.

Example business rules:

- “Each employee works in exactly one department; a department has many employees.”
 
-  “A project is controlled by one department; a department controls many projects.”

- “An employee may work on many projects; a project has many employees” (many-to-many via workson).
-  “An employee may have zero or many dependents; each dependent belongs to exactly one employee.”

-  “A department has one or more locations; a location belongs to exactly one department.”



## Example problems:

1. Consider the example relationship: $R_{\underline{A, B}, C, D, E}$ with FDS:
		$AB -> CDE$
		$C->D$
	a) is R in 2NF? Why or why not?

###### So for this, it is considered to be in 2NF since there are no partial dependencies


b) Is R in 3NF? Why or why not?

###### This would not be in 3NF since there is a transitive dependency. C needs AB, and then D needs C, creating this tension.


2. In the company database, explain what would happen (in terms of constraints) if you tru to delete an employee who still has dependents in the dependent relation

###### This would be an Referential integrity issue, since there are other instances that relied on that instance of employee. Since they are weak entities, then unless there is some logic to take care of that then they cannot exist on their own.

3. Give an example of an insert int PROJECT that would violate entity integrity in the company database.

###### An example would be if we try to create a new project without the Pnumber, which happens to be the primary key.

4. For an ER diagram with entities EMPLOYEE and DEPARTMENT and relationship WORKS_FOR, describe the possible cardinalities on each side and one business rule that matches a 1:N cardinality from DEPARTMENT to EMPLOYEE

###### So from the assignment, the amount of employees that participate in workson is just one, and each employee can work on many workson.

###### In a department, you can have multiple employees, but each employee can only belong to one department, hence, you have A department can have one to many employees.


5. Write relational notation for a generic DEPARTMENT with attributes: DeptNumber(PK), DeptName, ManagerSSN, ManagerStartDate

DEPARTMENT($\underline{DeptNumber}, DeptName, ManagerSSN, ManagerStartDate$)

###### So here, the department number is highlighted since this is the primary key.



6. Explain how a relational DBMS is self-describing. Give two specific things stored in the system catalog/data dictionary.

A relational DBMS is **self-describing** because it stores metadata about the database inside the database itself, in special system tables called the system catalog or data dictionary.


###### So would this be like the table name and the attribute names? 











