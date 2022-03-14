# Part 2: Implement MRU

## Implement MRU in PostgreSQL
Most (if not all) of your changes will be located in the directory: `$W$/postgresql-14.1/src/backend/storage/buffer/`. 

To implement the MRU algorithm, you will want to maintain the timestamp of each buffer when they are "used". For simplicity, you will maintain a global integer value which will be assigned to a buffer whenever a buffer page is "used", then, increment the integer. Initially, all buffers will have zero timestamp.

When you need to replace a buffer, you scan through the buffers, determine the candidate (not in use) buffers and evict the one with the most recent timestamp. 

## Print out log
To verify the correctness of your implementation, you need to print out the timestamp of all candidates (not in use) buffers as: 

`Candidate buffers: <a comma separated list of timestamps>`

and also explicitly print out the timestamp of the buffer that is going to be replaced as:

`Replaced buffer: <timestamp>`

An example of expected output is shown below. Please note that your output may have different timestamps, different amount of candidates for each replacement. That is possible. 
![mru](./figure/mru.png)

You can print out the log with the `printf` function in C programming language. It will print in your **server terminal**. 