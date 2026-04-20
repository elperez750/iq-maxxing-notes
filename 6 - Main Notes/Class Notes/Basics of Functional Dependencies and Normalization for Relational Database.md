


2026-04-11 11:51

Status:

Tags:

# Basics of Functional Dependencies and Normalization for Relational Database

##### Author: Ed Hoboken


## References



### Notes

## Informal Design Guidelines for Relation Schemas

The four informal guidelines to  measure the quality of relation schema design:

- Making sure that the semantics of the attributes is clear in the schema

###### So basically providing a clear name


- Reducing the redundant information in tuples

###### Not having two columns for the name seems like a good example of  this



- Reducing the NULL values in tuples

###### This makes sense. NULL could mean a lot of things so reducing this  is good practice



- Disallowing the possibility of generating spurious tuples.

###### Basically, this is so that when we decompose data and then join it again, we will not have data that does not correspond to be joined with other data. 



#### Imparting Clear Semantics to Attributes in Relations

The **Semantics** of a relation refers to its meaning resulting from the interpretation of attribute values in a tuple.


For example in a works_on table with SSN, Pnumber, and Hours, we can clearly see that this table represents the people working on a specific project


Another example is the project table, which clearly represents the project names, number, location which are specific to the actual project


![[Pasted image 20260411115716.png]]


###### The top image is an example of the semantics requirement of each table being violated. We can see that emp_proj and emp_dept have a lot of the same attributes, such as Ename, SSn, 


###### The update anomalies basically means that when we update a value such as SSN, we will have to update this in multiple tables.

#### Redundant Information in Tuples and Update Anomalies


###### The insert anomaly is not being able to insert a fact without some unrelated data.



![[Pasted image 20260411115907.png]]



![[Pasted image 20260411121028.png]]


Deletion Anomalies: The problem of deletion anomalies is related to the second
insertion anomaly situation just discussed. If we delete from EMP_DEPT an employee
tuple that happens to represent the last employee working for a particular depart-
ment, the information concerning that department is lost inadvertently from the
database. This problem does not occur in the database of Figure 14.2 because
DEPARTMENT tuples are stored separately.


###### Basically what this means is that deleting one fact will accidentally delete another fact, even if the other fact is needed.





Modification Anomalies: In EMP_DEPT, if we change the value of one of the attri-
butes of a particular department—say, the manager of department 5—we must
update the tuples of all employees who work in that department; otherwise, the
database will become inconsistent. If we fail to update some tuples, the same depart-
ment will be shown to have two different values for manager in different employee
tuples, which would be wrong.3
It is easy to see that these three anomalies are undesirable and cause difficulties to
maintain consistency of data as well as require unnecessary updates that can be
avoided; hence, we can state the next guideline as follows.


###### So the main takeaway here is do not have redundant attributes in two different tables, since if we were to delete an entry from one table which happened to be the name of the employee, then that change would then not be reciprocated throughout all the tables




#### NULL values in Tuples


- NULLs can lead to a waste of space in the table
- NULLs make the result of joins and counts unpredictable

###### The basic idea is, use NULLs as sparsely as possible. Always try to have some value in the table if you can.


#### Generation of Spurious Tuples

![[Pasted image 20260411121528.png]]


###### According to perplexity, spurious tuples are "fake" or meaningless rows that appear when you rejoin badly designed relations



###### To grasp my head around this, a tuple is fine if when you decompose it and then join it again it will be the same as it was before being decomposed.



#### Example:
Original relation:

- EMP_PROJ(Emp, Proj, Hours, Plocation)
    

Sample tuples:

- (E1, P1, 10, Seattle)
    
- (E1, P2, 5, Ellensburg)
    

Now decompose into:

- EMP_PROJ1(Emp, Proj, Hours, Plocation) – same as original but imagine some FDs motivating this
    
- EMP_LOCS(Emp, Plocation)
    

From the two tuples above, EMP_LOCS becomes:

- (E1, Seattle)
    
- (E1, Ellensburg)
    

If you then use EMP_PROJ1 and EMP_LOCS as base tables and natural join on Emp and Plocation, you can get combinations like:

- (E1, P1, 10, Seattle) – real
    
- (E1, P2, 5, Ellensburg) – real
    
- (E1, P1, 10, Ellensburg) – spurious
    
- (E1, P2, 5, Seattle) – spurious
    

The last two tuples never existed in the original EMP_PROJ; they say “E1 worked on P1 in Ellensburg” and “E1 worked on P2 in Seattle,” which are false in the original data.




###### So in the beginning, we can see that employee 1 worked on project 1 in Seattle and employee 1 worked on project 2 in Ellensburg. When we join these back together, it now says that E1 worked on Project 2 in Seattle which is obviously not true.



#### Summary and Discussion of Design Guidelines

The problems that were pointed out are:

- Anomalies that cause redundant work to be done during insertion into and modification of a relation, and that may cause accidental loss of information during a deletion from a relation

###### So basically, do not have the same attributes in multiple tables

- Waste of storage space due to NULLs and the difficulty of performing selections, aggregation operations, and joins due to NULL values.

###### NULLs make it hard to do aggregations, such as COUNTs and JOINs



- Generation  of invalid and spurious data during joins on base relations with matched attributes that may not represent a proper (foreign key, primary key) relationship



## Functional Dependencies


#### Definition of Functional Dependency


- Notation: X→Y means: in any legal instance of the relation, any two rows with the same X values must have the same Y values.
    
- X is the **determinant** (left side), Y is the dependent (right side). Example: StudentID → Name, Major, since one student ID maps to exactly one name and one major.

###### So that would be the same for the SSN for someone in the company right? We can map that to only one person. 


###### So in another table, we can expect the SSN to always map to that name.


## Normal Forms Based on Primary Keys


#### Normalization of Relations

This is
- A formal framework for analyzing relation schemas based on their keys and on the functional dependencies among their attributes


- A series of normal form tests that can be carried out on individual relation schemas so that the relational database can be normalized to any desired degree.




#### Practical Use of Normal Forms



#### Definitions of Keys and Attributes Participating in Keys



#### First Normal Form

- All rows must be unique
- Each cell must only contain a single value
- Each value should be non divisible

#### Second Normal Form

- Database must be in First Normal Form
- Non partial dependency - All non-prime attributes should be fully functionally dependent on the candidate key

###### Basically we want to reduce the redundancies here. If we had a table that had the student id, course id, and the course fee, this would not be in 2NF, since the course fee is not related to the student id. We are essentially repeating ourselves.

###### The fix would be to move the course id with the course fee. And then in the other table we would have the student id and the course id.


#### Third Normal Form

- Database must be in First and Second Normal form
- No transitive dependency - All fields must only be determined by the primary/composite key, not by other keys


For example if we had a table with tournament, year, winner, and date of birth. This would not be 3NF since the date of birth is only dependent on the actual winner.


###### So here, we know that the winner is associated with the tournament name and year, but the winner DOB is not dependent on tournament and year.


###### The tournament and year would be the composite key. This is what defines the winner. You cannot determine the winner just from the year or from the tournament. 


## Examples to work through


#### Question 1:

R(A,B,C,D,E,F)
FD1 (A,B,C,) -> D
FD2 B -> E
FD3 C -> F


Is the 1NF relation also in 2NF ?
Is the 2NF relation also in 3NF ?
What are the determinants in the 1NF relation?
###### The determinants are simply the primary keys in the relationship. I cannot highlight here but on the worksheet they are A, B, C


##### 1NF:
R(A, B, C, D, E, F)

Here we would have everything in the same relationship.

###### 2NF:

R1(A, B, C, D)
R2(B, E)
R3(C, F)

We separate things that do not depend on each other. For example, E does not depend on A,B,C. It would only depend on B



