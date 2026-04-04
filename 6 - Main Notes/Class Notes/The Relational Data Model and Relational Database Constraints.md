


2026-04-02 20:21

Status:

Tags:

# The Relational Data Model and Relational Database Constraints

##### Author:


## References
- https://www.geeksforgeeks.org/dbms/relational-model-in-dbms/

- https://runestone.academy/ns/books/published/practical_db/PART3_RELATIONAL_DATABASE_THEORY/01-relational-model/relational-model.html

- https://www.turingmachine.org/courses/2005/csc370K05/assign/db-ch3.pdf

### Notes


## Relational Model Concepts

- The relational model represents the database a s a collection of relations.
- When a relation is thought of as a table of values, each row in the table represents a collection of related data values.

###### So to illustrate this point, students would be one table, and that is related to classes, and they are all related to grades


### Domains, Attributes, Tuples, and Relations

- This will basically be the possible characters or numbers that can be in a field

###### A great example would be phone numbers in Washington. All of the phone numbers can either start with 425, 509, 206, 253, and 360.

###### A name is contained within the characters of the alphabet, that being 26

#### Some more examples:

- Usa_phone_numbers. The set of ten-digit phone numbers valid in the United
States.
- Local_phone_numbers. The set of seven-digit phone numbers valid within a
particular area code in the United States. The use of local phone numbers is
quickly becoming obsolete, being replaced by standard ten-digit numbers.
-  Social_security_numbers. The set of valid nine-digit Social Security numbers.
(This is a unique identifier assigned to each person in the United States for
employment, tax, and benefits purposes.)
-  Names: The set of character strings that represent names of persons.
-  Grade_point_averages. Possible values of computed grade point averages;
each must be a real (floating-point) number between 0 and 4.
-  Employee_ages. Possible ages of employees in a company; each must be an
integer value between 15 and 80.
-  Academic_department_names. The set of academic department names in a
university, such as Computer Science, Economics, and Physics.
- Academic_department_codes. The set of academic department codes, such as
‘CS’, ‘ECON’, and ‘PHYS’.


 A relation schema R is denoted by R($A_1, A_2, ..., A_{n}$) is made up of a relation name R and a list of attributes 

So a relation of degree seven, would be the following:

STUDENT(Name, Ssn, Home_phone, Address, Office_phone, Age, Gpa)

###### This is degree 7 because it has 7 attributes.

![[Pasted image 20260402203035.png]]

###### So the relation name is basically the name of the column, and then the tuples are the individual values? So a tuple for me would be: "Name: Elliott Perez, SSn:xxx" etc.


### Characteristics of Relations


#### Ordering of Tuples in a Relation
- A relation is defined as a set of tuples.
- Elements of a set have no ordering


#### Ordering of Values within a Tuple and an Alternative Definition of a Relation
- an n-tuple is an ordered list of n values
-
![[Pasted image 20260403155241.png]]



![[Pasted image 20260403155256.png]]



###### So depending on the ordering property, these could be represented in different ways.  As we see in this example, the name is first, and then in the second tuple, we see that address is first. 



###### Usually the first definition is used, where the attributes are ordered in the relation schema and the values within tuples are similarly ordered



There are usually several meanings for NULL values, such as value unknown, value exists but is not available, or attribute does not apply to this tuple.




## Relational Model Constraints and Relational Database Schemas

Constraints can be divided into three main categories:

- Constraints that are inherent in the data model. We call these inherent model-based constraints or implicit constraints




- Constraints that can be directly expressed in the schemas of the data model, typically by specifying them in the DDL (data definition language). We call these schema-based constraints or explicit constraints.



- Constraints that cannot be directly expressed in the schemas of the data model, and hence must be expressed and enforced by the application programs or in some other way. We call these application-based or semantic constraints or business rules.



### Domain constraints:
- each attribute must be an atomic value from the domain dom(A)

###### Maybe this means that they must all be integers for example, or floats? Not too sure on that.


### Key Constraints and Constraints on NULL Values


- By definition, all elements of a set are distinct; hence, all tuples in a relation must also be distinct.
- Any such set of attributes SK is called a super key of the relation schema R


###### So basically the super key is just the name itself? Or the SSN??

A key satisfies two properties:
- Two distinct tuples in any state of the relation cannot have identical values for all the attributes in the key. This uniqueness property also applies to a super key

###### So yeah that makes sense for example in a college database, we cannot have two Elliott' that are the same person. We can have the same name, but not the same ID.

- It is a minimal super key. That is, a super key from which we cannot remove any attributes and still have the uniqueness constraint hold. This minimality property is required for a key but is optional for a super key.



Consider the STUDENT relation of
Figure 5.1. The attribute set {Ssn} is a key of STUDENT because no two student
tuples can have the same value for Ssn. Any set of attributes that includes Ssn—for
example, {Ssn, Name, Age}—is a superkey. However, the superkey {Ssn, Name, Age}
is not a key of STUDENT because removing Name or Age or both from the set still
leaves us with a superkey. In general, any superkey formed from a single attribute is
also a key. A key with multiple attributes must require all its attributes together to
have the uniqueness property.



######  Ok this makes way more sense. Essentially, the SSN alone acts as a key since it must be unique, but when paired with the name, age, and ssn, it creates a super key, which is obviously unique, since those three attributes will not be the same as other values in the database. 


###### The good thing to is that you can remove elements from the set and it can still be considered a super key. So we can remove name and it would still be a super key, since that combo of ssn and age will be a unique identifier.


![[Pasted image 20260403161833.png]]


###### So these are considered candidate keys since they are a unique identifier in the CAR object. For example, the license plate number and the engine serial number are always going to be unique, so we can use either of these as the primary key.


### Relation Databases and Relational Database Schemas

- A **Relational database schema** S is a set of relation schemas S ={$R_1, R_2, ... R_M$} and a set of integrity constraints IC.
- A **Relational database state** DB of S is a set of relation states DB={$r_1, r_2, ..., r_m$} such that the relation states satisfy the integrity constraints specified in IC.


![[Pasted image 20260403162555.png]]




![[Pasted image 20260403162845.png]]




## Entity Integrity, Referential Integrity, and Foreign Keys


- The **Entity integrity constraint** states that no primary key value can be NULL.
- The **Referential integrity constraint** is specified between two relations and is used to maintain the consistency among tuples in the two relations.

- To define the referential integrity more formally, first we define the concept of a foreign key.

A key is a foreign key if the following is satisfied:
- The attributes in FK have the same domain as the primary key attributes PK of $R_2$; the attributes FK are said to reference or refer to the relation $R_2$
- A value of FK in a tuple $t_1$ of the current state $r_1$ either occurs as a value of PK for some tuple $t_2$ in the current state $r_2$ or is NULL. In the former case, we have $t_1=t_{2}$, and we say that the tuple $t_1$ references or refers to the tuple $t_2$

###### From what I know, the foreign key is used to refer to other tables



![[Pasted image 20260403171630.png]]


###### So here, it seems like a FK is the SSN, since it appears in the dependent table, works on table, and department table.


### Other Types of Constraints
- Another set of constraints is the semantic integrity constraint, which are not part of the DDL and have to be specified and enforced in a different way.

Examples:
- salary of an employee should not exceed the salary of the employee's supervisor
- The maximum number of hours an employee can work on all projects per week is 56.

## Update Operations, Transactions, and Dealing with Constraint Violations

There are three main modification updates; Update, Delete, and Create.




### The Insert Operation


#### Operation:
- Insert <‘Cecilia’, ‘F’, ‘Kolonsky’, NULL, ‘1960-04-05’, ‘6357 Windy Lane, Katy,
TX’, F, 28000, NULL, 4> into EMPLOYEE.
- Result: This insertion violates the entity integrity constraint (NULL for the
primary key Ssn), so it is rejected.


###### Since this is the key we use to determine if other inputs are unique, then it cannot be null. This is crucial information

#### Operation:
- Insert <‘Alicia’, ‘J’, ‘Zelaya’, ‘999887777’, ‘1960-04-05’, ‘6357 Windy Lane, Katy,
TX’, F, 28000, ‘987654321’, 4> into EMPLOYEE.
- Result: This insertion violates the key constraint because another tuple with
the same Ssn value already exists in the EMPLOYEE relation, and so it is
rejected.


###### Duplicate value

#### Operation:
- Insert <‘Cecilia’, ‘F’, ‘Kolonsky’, ‘677678989’, ‘1960-04-05’, ‘6357 Windswept,
Katy, TX’, F, 28000, ‘987654321’, 7> into EMPLOYEE.
- Result: This insertion violates the referential integrity constraint specified on
Dno in EMPLOYEE because no corresponding referenced tuple exists in DEPARTMENT with Dnumber = 7.

###### The department 7 does not exist, therefore the insertion is rejected.


### The Delete Operation

#### Operation:
- Delete the WORKS_ON tuple with Essn = ‘999887777’ and Pno = 10.
- Result: This deletion is acceptable and deletes exactly one tuple.
#### Operation:
- Delete the EMPLOYEE tuple with Ssn = ‘999887777’.
- Result: This deletion is not acceptable, because there are tuples in WORKS_ON that refer to this tuple. Hence, if the tuple in EMPLOYEE is deleted, referential integrity violations will result.
#### Operation:
- Delete the EMPLOYEE tuple with Ssn = ‘333445555’.
- Result: This deletion will result in even worse referential integrity violations, because the tuple involved is referenced by tuples from the EMPLOYEE, DEPARTMENT, WORKS_ON, and DEPENDENT relations.


### The Update Operation

#### Operation:
- Update the salary of the EMPLOYEE tuple with Ssn = ‘999887777’ to 28000.
- Result: Acceptable.
#### Operation:
- Update the Dno of the EMPLOYEE tuple with Ssn = ‘999887777’ to 1.
- Result: Acceptable.
#### Operation:
- Update the Dno of the EMPLOYEE tuple with Ssn = ‘999887777’ to 7.
- Result: Unacceptable, because it violates referential integrity.
#### Operation:
- Update the Ssn of the EMPLOYEE tuple with Ssn = ‘999887777’ to ‘987654321’.
- Result: Unacceptable, because it violates primary key constraint by repeating a value that already exists as a primary key in another tuple; it violates referential integrity constraints because there are other relations that refer to the existing value of Ssn.


## Quick mental model (to cement things)

Think of a simple university database:

- `STUDENT(Sid PK, Name, Age, Gpa)`
    
- `COURSE(Cid PK, Title, Dept)`
    
- `ENROLL(Sid FK→STUDENT.Sid, Cid FK→COURSE.Cid, Grade)`
    
- Domains:
    
    - `Sid`: integers 100000–999999.
        
    - `Gpa`: real 0–4.
        
- Keys:
    
    - `STUDENT`: candidate key `{Sid}`.
        
    - `ENROLL`: primary key `{Sid, Cid}` (composite key).
        
- Constraints:
    
    - Entity integrity: `Sid`, `Cid` not NULL.
        
    - Referential: every `Sid` in `ENROLL` must exist in `STUDENT`, every `Cid` in `ENROLL` must exist in `COURSE`.


