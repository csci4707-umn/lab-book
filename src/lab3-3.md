# Part 3: Joining Performance

<!-- EXPLAIN ANALYZE
SELECT T.*
FROM trip T, station S
WHERE S.station_name = 'Coffman Union'
  AND T.start_station_id = S.station_id; -->

## Test Queries

You will need to find how index affects join performance using following query:

1. Find all trips start from the station **Coffman Union**.

You will keep the table **station** un-indexed and use different **trip** tables and indexes that you created in [Part2](./lab3-2.md) to test the join performance. 

<span style="color: red;">Answer question 3.1 in lab report.</span>

## Test 1: No index

Test the join against the **trip** table. 

<span style="color: red;">Answer question 3.2 in lab report.</span>

## Test 2: Hash index

Test the join against **trip_hash** table. 

<span style="color: red;">Answer question 3.3 in lab report.</span>

## Test 3: B-tree index (clustered)

Test the join against **trip_btree** table. 

<span style="color: red;">Answer question 3.4 in lab report.</span>

## Finish Lab Report
<span style="color: red;">Answer question 3.1 - 3.5 in lab report.</span>