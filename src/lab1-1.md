# Part 1: ProjectDB Schema Creation

ProjectDB consists of the following relations defined in the following schemas. Please create tables for them in PostgreSQL.

>University (  
>UnivId: NUMERIC  
>UnivName: VARCHAR(40)  
>)

>Department (  
>DeptId: NUMERIC  
>DeptName: VARCHAR(40)  
>)

>Employee (  
>EmpId: NUMERIC  
>EmpName: VARCHAR(40)  
>DeptId: NUMERIC REFERENCES Department(DeptId)  
>HomeZipCode: NUMERIC  
>)

>Project (  
>ProjId: NUMERIC  
>ProjName: VARCHAR(40)  
>)

>Graduate (  
>EmpId: NUMERIC REFERENCES Employee(EmpId)  
>UnivId: NUMERIC REFERENCES University(UnivId)  
>GradYear: NUMERIC  
>)
  
>EmpProject (  
>EmpId: NUMERIC REFERENCES Employee(EmpId)  
>ProjId: NUMERIC REFERENCES Project(ProjId)  
>)

>ProjectManager (  
>ProjId: NUMERIC REFERENCES Project(ProjId)  
>MgrId: NUMERIC REFERENCES Employee(EmpId)  
>)

## What to Submit?
The submission of your work is a file named `p1.sql`, that contains all SQL queries to create the above relations.

## Grading Criteria:
- Total: 20 points
  - 10 Points: The provided script is able to create all the above relations with the correct schema.
  - 10 Points: The provided script handles the FOREIGN KEY constraint perfectly.
