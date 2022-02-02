# Part 2: SQL Queries

Once you have created the above schema, run the `data.sql` file to load the data into the database.

<pre><code>\i &#60;path-to-data.sql&#62;</code></pre>

Then, write SQL queries that answer the questions below (one SQL query per question but you are allowed to use nested queries). The query answers should be duplicate-free, but you should use distinct only when necessary.

1. Find the names of the employees who are living in Minneapolis (Zip code 55414 or 55455).

2. Find the names of the projects that are currently managed by any manager.

3. For each project, display its name as well as the number of employees who are currently working on it except for a project without any employees.

4. Find the name(s) of the university/universities that graduated the maximum number of distinct managers.

5. For each employee, say E, display the name of E, the department name of E, and the graduation year of E.

6. Display the name of the project that has the maximum number of different employees who worked/"are working" on it. If more than one project qualify, display all the qualified projects. (Hint: refer to EmpProject only and not ProjectManager).

## What to Submit?
The submission of your work is a file named `p2.sql`, that contains all the above SQL queries.

## Grading Criteria:
- 10 Points (no partial credit) for each correct SQL query.