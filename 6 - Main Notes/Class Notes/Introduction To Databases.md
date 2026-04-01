
2026-03-31 19:34

Status:

Tags:

# Introduction To Databases

##### Author: Ed Hoboken


## References



### Notes

## Examples of databases in real life

- Money in a bank account
- Computerized library catalog
- Online purchases

###### Basically everything is stored in a database. Now the requirements for the amount of data needing to be stored is much higher, as [[AI]] models now need to store all of their training data somewhere


## What is a database
#### A database is a collection of related data

#### By data, we mean know facts that can be recorded and have implicit meaning.


**Database management system (DBMS)** - This is a computerized system that enables users to create and maintain a database.

A **database** is a collection of related data, organized so it can be meaningfully interpreted and efficiently accessed.

#### A database has the following:

- Data types
- Structures
- constraints of the data

#### Constructing the database is a process of storing the data on some storage medium

#### Manipulating a database includes functions such as querying the database to retrieve specific data.




#### Simplified database system environment
![[Pasted image 20260331195636.png]]



#### Database manipulation involves querying and updating. Examples are:

- Retrieve the transcript—a list of all courses and grades—of ‘Smith’ 
- List the names of students who took the section of the ‘Database’ course  offered in fall 2008 and their grades in that section
- List the prerequisites of the ‘Database’ course 

#### Database updates include the following:

- Change the class of ‘Smith’ to sophomore 
- Create a new section for the ‘Database’ course for this semester 
- Enter a grade of ‘A’ for ‘Smith’ in the ‘Database’ section of last semester 


## Characteristics of the Database Approach


#### The main characteristics of the database approach versus the file-processing approach are the following:

- Self-describing nature of a database system
- Insulation between programs and data, and data abstraction

###### I'm guessing that this means that the data lives in the data base, and the frontend is a separate things that is connected to the database.


- Support of multiple views of the data
- Sharing of data and multiuser transaction processing


### Self-Describing nature of a Database System

#### Data is stored as self-describing data that includes the data item names and values together

- In traditional file‑processing, each application owns its files and embeds file formats in code; changes to data structure force changes in all programs that read those files.

###### Kind of like key value pairs in a dictionary??


### Insulation between Programs and Data, and Data Abstraction


#### Traditional file processing has data files embedded in the application programs, so any changes to the structure of a file may require changing all programs that access the file

#### DBMS access programs do not require such changes

#### This is called program-data independence

#### The key separation is logical schema vs physical storage; DB can reorganize files or add indexes without changing my queries.

###### Essentially, if we change the schema of a student table and add phone number, in a DBMS system, when we add a new student, they will now possess this attribute

### Support of multiple views of the data


#### Different views are provided for different use cases. For example, one user might want to only access and print transcripts. The other user might be interested in checking students who have taken prerequisites.


###### I always thought that users could access everything. It seems that views may be limited depending on level of access. Like a teacher might only be able to update grades, whereas the user would have the ability to just view grades.



### Sharing of Data and Multiuser Transaction Processing


#### Essentially, the DBMS must account for multiple users trying to access information or change information


###### A good example would be if someone is looking to buy a plane ticket. The system must keep track of changes made, since there are probably multiple users trying to buy a plane ticket for a specific flight.


**Transaction** - This is executing a program or process that includes one or more database accesses, such as reading or updating database records

###### From what I've heard about these, it basically means that multiple updates must be made in order for the transaction to be successful. If one component of the transaction fails, then the transaction does not go through

**Atomicity** - This ensures that either all the data base operations ins a transaction are executed or none are
###### So I got my last definition mixed up. That one belongs to atomicity

**Isolation** - This ensures that each transaction appears to execute in isolation from other transactions

###### I mean I see this when buying tickets, since there are probably multiple people buying tickets to an event. The database must keep track of all of those and update accordingly


## Actors on the Scene


### Database Administrators


#### Essentially manage resources. They will decide access permissions, coordinate and monitor the database use, and acquiring software and hardware resources as needed.


###### So basically managing permissions and making sure that database transactions are succeeding and not failing


### Database Designers

#### These are the people responsible for figuring out the data types, as well as the appropriate structures to use for the data before the database is implemented.

#### These people will interact with clients to figure out their needs.

###### Basically these people will design the schemas and figure out the data types


### Different types of users

- Casual users: People that occasionally use the database, but may need different information each time
- Naive or parametric end users - Their main job function revolves around constantly querying and updating the database

###### So basically these people are just the people that are looking up if a store has an item, or if a certain room is available. This is the most common user


- sophisticated end users - Includes engineers, scientists, business analysts, and others who thoroughly familiarize themselves with the facilities of the DBMS in order to implement their own applications to meet their complex requirements



- maintain personal databases by using ready-made program packages that provide easy-to -use menu-based or graphics-based interfaces. An example is the user of a financial software package that stores a variety of personal financial data. 



## Advantages  of using the DBMS approach


### Controlling Redundancy

#### In the database approach, the views of different user groups are integrated during  database design.

**Data Normalization**- This is when the database =design stores each logical data item - such as a students name or birth date in only one place in the database.

###### So basically not having birth date for two different tables, only having it in the students table


![[Pasted image 20260331203724.png]]


### Restricting Unauthorized Access


#### When database has many users, not all users should be able to access sensitive data, such as financial data


#### A DBMS should  provide a security and authorization subsystem, which the DBA uses to create  accounts and to specify account restrictions


#### For example, only the DBA’s staff may be allowed to use certain  privileged software, such as the software for creating new accounts.


###### Essentially, do not let the new hire be able to delete employee names from the database. That would be essentially firing them.



### Providing Persistent Storage for Program Objects

#### Databases can be used to provide persistent storage for program objects and data  structures. 

#### The persistent storage of program objects and data structures is an important function of database systems



### Providing Storage Structures and Search Techniques for Efficient Query Processing

#### Indexes are often used to speed up the process of executing queries on disk, since the database is usually stored in disk.


#### Therefore, the DBMS often has a buffering or caching module that maintains parts  of the database in main memory buffers


###### Basically, the database will cache results that are queried most often. Maybe this could be the prices of a concert that is very popular, like a Taylor Swift concert



### Providing Backup and Recovery

#### A DBMS must provide facilities for recovering from hardware or software failures.  The backup and recovery subsystem of the DBMS is responsible for recovery.


###### This seems like redundancy, which is something that was said to not be a part of a DBMS. I wonder what the solution for this would be. Maybe incremental changes, where a state of the database at a certain time is always saved.

### Providing Multiple User Interfaces

#### Because many types of users with varying levels of technical knowledge use a database, a DBMS should provide a variety of user interfaces.


###### So for example, users like software engineers might access data directly using SQL, and customers who might not know about SQL might just access data by pressing a button, such as the "Check available seats" button on a ticket selling application such as Ticketmaster.




### Representing Complex Relationships among Data

#### A database may include numerous varieties of data that are interrelated in many  ways.


###### So basically in a school system, a student would be related to grade, teacher, major, and all of these different things. There are relationships between all of these things.


### Enforcing Integrity Constraints 

#### Most database applications have certain integrity constraints that must hold for  the data


###### The most common seems to be data types. For example, the student name can most likely not be an integer, and the age can no likely be a string. This is common sense

###### This might also include size of a certain field. Maybe name has to be less than 100 characters, since realistically most people do not have a name that is that long, and if the constraint were longer, people would be able to have longer names which would obviously take up more space.


###### This could also include uniqueness.


### Permitting Inferencing and Actions Using Rules and Triggers

#### Some database systems provide capabilities for defining deduction rules for inferencing new information from the stored database facts. 

###### So in the example of a school database, this could be logic set in place to determine whether a student is on probation based on grades

###### The logic could take into account the number of absences, number of failed classes since they started, and much more.


## When Not to Use a DBMS

#### There may be some instances where the overhead of using the DBMS may be too high for the applications that it will be used.

- High initial investment in hardware, software, and training 
- The generality that a DBMS provides for defining and processing data
- Overhead for providing security, concurrency control, recovery, and integrity function

###### So basically, if it is a small company, it is not worth it to invest in a DBMS, since the functions of it will be too advanced




#### It may be desirable to develop customized database applications under the following circumstances:
- Simple, well defined database applications that are not expected to change at all
- Stringent, real time requirements for some application programs that may not be met because of DBMS overhead
- Embedded systems with limited storage capacity, where a general-purpose DBMS would not fit
- no multiple user access to data.

###### So a personal project most likely

