# Part 2: Single Table Lookup Performance

## Important Command

To show each query's execution plan and measure its execution time, add **EXPLAIN ANALYZE** in front of each query. See [document](https://www.postgresql.org/docs/current/sql-explain.html) for examples. 

For example, 
<pre><code>EXPLAIN ANALYZE SELECT * FROM trip;</code></pre>

## Test Queries
You will need to find how index affects performance on the following queries:

1. (equality search) Find all trips (use select *) with start_station_id = 30001.
2. (range search) Find all trips (use select *) with start_station_id greater than 30001 and less than 30010.

Run both queries **multiple times** in each of the following test. Observe its **QUERY PLAN** and compute its average **Execution Time**.

<span style="color: red;">Answer question 2.1 in lab report.</span>

## Test 1: No index

Test the two queries against the **trip** table. 

<span style="color: red;">Answer question 2.2 in lab report.</span>

## Test 2: Hash index

First, create a hash index for table **trip_hash** on column **start_station_id** using following command ([Reference](https://www.postgresql.org/docs/current/indexes-types.html)):

<pre><code>CREATE INDEX &#60;index_name&#62; ON &#60;table_name&#62; USING HASH (&#60;column_name&#62;);</code></pre>

For example,
<pre><code>CREATE INDEX trip_hash_index ON trip_hash USING HASH (start_station_id);</code></pre>

Test the two queries against the **trip_hash** table.

<span style="color: red;">Answer question 2.3 in lab report.</span>

## Test 3: B-tree

First, create a b-tree index for table **trip_btree** on column **start_station_id** using following command ([Reference](https://www.postgresql.org/docs/current/sql-createindex.html)):

<pre><code>CREATE INDEX &#60;index_name&#62; ON &#60;table_name&#62;(&#60;column_name&#62;);</code></pre>

For example,
<pre><code>CREATE INDEX trip_btree_index ON trip_btree (start_station_id);</code></pre>

Test the two queries against the **trip_btree** table.

<span style="color: red;">Answer question 2.4 in lab report.</span>


## Test 4: Clustered b-tree

Creating b-tree index does not cluster the data by default. To cluster the data, use following command ([Reference](https://www.postgresql.org/docs/14/sql-cluster.html)):

<pre><code>CLUSTER &#60;index_name&#62; ON &#60;table_name&#62;;</code></pre>

For example,
<pre><code>CLUSTER trip_btree_index ON trip_btree;</code></pre>

Test the two queries against the **trip_btree** table again.

<span style="color: red;">Answer question 2.5 in lab report.</span>

## Finish Lab Report
<span style="color: red;">Answer question 2.1 - 2.6 in lab report.</span>