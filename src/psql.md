# PostgreSQL 101

You are supposed to learn how to use PostgreSQL on you own. Specific SQL grammar (dialect) is not the focus on this course. This tutorial only aims to help you start the labs. The code blocks on this page are aimed for examples, not for copy-and-run. 

### All sql in PostgreSQL end with a ";"
`psql` waits for a `;`, then it knows it is an end for the sql. To run an SQL, type your sql, end with a `;` then hit `Enter`.

```
ProjectDB=# CREATE TABLE student (sid integer, name text);
CREATE TABLE
ProjectDB=# DROP TABLE student;
DROP TABLE
```

This means you can type sql in multiline in `psql`. Type your sql in multiline, end with a `;` then hit `Enter`. When you are in the first line of your sql, line starts with `=#`; when you are in brackets, line starts with `(#`, otherwise line starts with `-#`.

```
ProjectDB=# CREATE TABLE
ProjectDB-# student
ProjectDB-# (
ProjectDB(# sid integer,
ProjectDB(# name text
ProjectDB(# )
ProjectDB-# ;
CREATE TABLE
```

### Helpful commands in `psql`

In addition to SQL, `psql` has many helpful commands.

1. You must exit psql by typing `\q` and do not use `ctrl-c`.
```
ProjectDB=# \q
```

2. To show relations you have created, use `\d`
```
ProjectDB=# \d
          List of relations
 Schema |  Name   | Type  |  Owner
--------+---------+-------+----------
 public | student | table | huan1531
(1 row)
```

3. To show schema of a relation, use `\d <relation-name>`
```
ProjectDB=# \d student
              Table "public.student"
 Column |  Type   | Collation | Nullable | Default
--------+---------+-----------+----------+---------
 sid    | integer |           |          |
 name   | text    |           |          |
```

4. To run an sql script located at `$W$/script.sql`, use `\i $W$/script.sql`

### An example SQL script

Just like `.sh` file for shell, `.sql` file is an executable file for `psql`, containing one or more sql queries. 

Create a new file `script.sql` in `$W$`. Copy the following to the file. 

```
/*
 * script.sql
 * A .sql script example
 */

-- Single line comment in .sql file starts with "--"

/*
 * Multiline comment is wrapped by "/" and "*"
 */

-- Drop table if exists
DROP TABLE IF EXISTS student;

-- Create table
CREATE TABLE student (
    sid integer,
    name text
);

-- Insert value into table
INSERT INTO student VALUES (1, 'John');
INSERT INTO student VALUES (2, 'Sam');
INSERT INTO student VALUES (3, 'Mark');
INSERT INTO student VALUES (4, 'Ted');
INSERT INTO student VALUES (5, 'Ross');
INSERT INTO student VALUES (6, 'James');
INSERT INTO student VALUES (7, 'Tom');

-- Do some sample queries
-- 1. Select all from table, '*' return all attributes
SELECT * FROM student;

-- 2. What is Ross's student ID
SELECT sid
FROM student
WHERE name = 'Ross';

-- 3. Who are the students with ID less than 3
select sid from student where sid < 3;
```

> As you can tell from the last query, SQL is case insensitive. However, it is always good to follow some style guides, for example this [guide](https://www.sqlstyle.guide/).

Save the file and go back into `psql`. To run the script, use `\i $W$/script.sql`.
```
ProjectDB=# \i $W$/script.sql
DROP TABLE
CREATE TABLE
INSERT 0 1
INSERT 0 1
INSERT 0 1
INSERT 0 1
INSERT 0 1
INSERT 0 1
INSERT 0 1
 sid | name
-----+-------
   1 | John
   2 | Sam
   3 | Mark
   4 | Ted
   5 | Ross
   6 | James
   7 | Tom
(7 rows)

 sid
-----
   5
(1 row)

 name
------
 John
 Sam
(2 rows)
```

`.sql` file can also be passed as an argument to `psql`, so you can run a `.sql` file without going into `psql`. Copy and run following command in your terminal. 

<pre><code>bin/psql ProjectDB -f $W$/script.sql</code></pre>

You should see the following output. 

```
$ bin/psql ProjectDB -f $W$/script.sql
DROP TABLE
CREATE TABLE
INSERT 0 1
INSERT 0 1
INSERT 0 1
INSERT 0 1
INSERT 0 1
INSERT 0 1
INSERT 0 1
 sid | name
-----+-------
   1 | John
   2 | Sam
   3 | Mark
   4 | Ted
   5 | Ross
   6 | James
   7 | Tom
(7 rows)

 sid
-----
   5
(1 row)

 name
------
 John
 Sam
(2 rows)
```

### Use online sources