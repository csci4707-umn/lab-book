# Part 1: ProjectDB Schema Creation

ProjectDB consists of the following relations defined in the following schemas. Please create tables for them in PostgreSQL.

#### Important Update (02/08)
- Primary keys are underlined for each relation. You need to include them in your `CREATE TABLE` statements. 
- Include the following constrain with `ON DELETE` actions in your `CREATE TABLE` statements. 
  - When a project is removed from record, we no longer keep records for `EmpProject` and `ProjectManager`.
- You may find these parts of document useful for this lab
  - [Create table related](https://www.postgresql.org/docs/14/ddl.html)
  - [Query related](https://www.postgresql.org/docs/14/queries.html)
  - [Insert/delete related](https://www.postgresql.org/docs/14/dml.html)

>University (  
>&nbsp;&nbsp;<u>UnivId</u>: NUMERIC  
>&nbsp;&nbsp;UnivName: VARCHAR(40)  
>)

>Department (  
>&nbsp;&nbsp;<u>DeptId</u>: NUMERIC  
>&nbsp;&nbsp;DeptName: VARCHAR(40)  
>)

>Employee (  
>&nbsp;&nbsp;<u>EmpId</u>: NUMERIC  
>&nbsp;&nbsp;EmpName: VARCHAR(40)  
>&nbsp;&nbsp;DeptId: NUMERIC REFERENCES Department(DeptId)  
>&nbsp;&nbsp;HomeZipCode: NUMERIC  
>)

>Project (  
>&nbsp;&nbsp;<u>ProjId</u>: NUMERIC  
>&nbsp;&nbsp;ProjName: VARCHAR(40)  
>)

>Graduate (  
>&nbsp;&nbsp;<u>EmpId</u>: NUMERIC REFERENCES Employee(EmpId)  
>&nbsp;&nbsp;UnivId: NUMERIC REFERENCES University(UnivId)  
>&nbsp;&nbsp;GradYear: NUMERIC  
>)
  
>EmpProject (  
>&nbsp;&nbsp;<u>EmpId</u>: NUMERIC REFERENCES Employee(EmpId)  
>&nbsp;&nbsp;<u>ProjId</u>: NUMERIC REFERENCES Project(ProjId)  
>)

>ProjectManager (  
>&nbsp;&nbsp;<u>ProjId</u>: NUMERIC REFERENCES Project(ProjId)  
>&nbsp;&nbsp;<u>MgrId</u>: NUMERIC REFERENCES Employee(EmpId)  
>)

## What to Submit?
The submission of your work is a file named `p1.sql`, that contains all SQL queries to create the above relations.

## Grading Criteria:
- Total: 20 points
  - 10 Points: The provided script is able to create all the above relations with the correct schema.
  - 10 Points: The provided script handles the FOREIGN KEY constraint perfectly.
