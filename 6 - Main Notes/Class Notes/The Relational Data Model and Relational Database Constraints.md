


2026-04-02 20:21

Status:

Tags:

# The Relational Data Model and Relational Database Constraints

##### Author:


## References



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





