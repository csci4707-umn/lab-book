# Installation

We first download and install PostgreSQL, then we initialize a folder for PostgreSQL to keep data.

## Pre-request
1. You should be able to connect to any CSE UNIX/Linux machines. See detail on this [page](./machine.md)
2. PostgreSQL is a large software. You will want at least 200 MB of space in your machine. If not, learn how to free your space on this [page](https://cse.umn.edu/cseit/self-help-guides/disk-quota-free-your-space).

## Install PostgreSQL

1. Download version 14.1 of PostgreSQL.
<pre><code>wget https://ftp.postgresql.org/pub/source/v14.1/postgresql-14.1.tar.gz</code></pre>

2. Extract.
<pre><code>tar xvzf postgresql-14.1.tar.gz</code></pre>

3. Create an installation folder, called “install”.
<pre><code>mkdir install</code></pre>

Then, we retrieve the full path of both source and installation folder by executing the following command:

4. Retrieve the full path of the directory.
<pre><code>pwd</code></pre>

This will return a full path of your current directory. Throughout this documentation, this path is referred as `$W$`. So, don’t forget to replace it with your actual working directory. Thus, the path of the PostgreSQL’s source code is located at `$W$/postgresql-14.1` and the path where we will install PostgreSQL is located at `$W$/install`.

Next, you will configure the installation of PostgreSQL and install PostgreSQL on the given path.

5. Go to the source directory.
<pre><code>cd postgresql-14.1</code></pre>

6. Run the configure command. **Don’t forget to change $W$ to your actual directory.**
<pre><code>./configure --prefix=$W$/install</code></pre>

7. Run the makefile.
<pre><code>make</code></pre>

8. Run the installation.
<pre><code>make install</code></pre>

## Initialize Database

After the installation has finished, you will need to initialize and create a database to use. In this example, we will initialize the database at `$W$/install/data` folder.

9. Go to the installation folder.
<pre><code>cd ../install</code></pre>

10. Initialize database store.
<pre><code>bin/initdb -D data</code></pre>
Once the database has been initialized, we can start the PostgreSQL backend.