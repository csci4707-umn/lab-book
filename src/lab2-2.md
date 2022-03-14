# Part 2: Compile and Test

## Change PostgreSQL config
To test your changes, you will first need to change the memory size of PostgreSQL. Since the test case that is given to you is very small compared to the default memory size of PostgreSQL, it is a good idea to change the memory size in the configuration file of the PostgreSQL. 

The configuration is located in: `$W$/install/data/postgresql.conf`. You will change the shared_buffer size to shared_buffers = 128kB.

## Compile your changes
To compile your changes, you must run the following three commands from the source directory, i.e., `$W$/postgresql-14.1`. Remember to shutdown your server before you make a new compiling:

1. Clean the executable.

<pre><code>make clean</code></pre>

2. Remake

<pre><code>make</code></pre>

3. Install the changes. 
   
<pre><code>make install</code></pre>

If you get no error in this process, you will be able to start and server and client and test your changes. 

## Test your changes
To test your change, run the test_data/buffer_add.sql file and look at the replaced buffer’s timestamp compared to all other candidate buffers’ timestamp. In order to run buffer_add.sql, you need to make one modification to the file. Please make sure you change the path of test_data/values10k.dat file according to its location.