# Part 1: Understand MRU and Code

## MRU
The basic idea of MRU can be seen in [here](https://en.wikipedia.org/wiki/Cache_replacement_policies#Most_recently_used_(MRU)). However, you will need to adapt the algorithm with the Database buffer management policy concept. 

## Implement MRU in PostgreSQL
Most (if not all) of your changes will be located in the directory: `$W$/postgresql-14.1/src/backend/storage/buffer/`. 

To implement the MRU algorithm, you will want to maintain the timestamp of each buffer when they are "used". For simplicity, you will maintain a global integer value which will be assigned to a buffer whenever a buffer page is "used", then, increment the integer. Initially, all buffers will have zero timestamp.

When you need to replace a buffer, you scan through the buffers, determine the candidate (not in use) buffers and evict the one with the most recent timestamp. 

## Questions (15 pts)
These questions are designed to let you start early and guide you through the codebase. Answer the following questions on Gradescope. 

Please answer the following questions based on the original code of PostgreSQL 14.1:

1. There are five files under `$W$/postgresql-14.1/src/backend/storage/buffer/`. What is each file's job? Answer for each file in one sentence. (5 pts)
- buf_init.c
- buf_table.c
- bufmgr.c
- freelist.c
- localbuf.c

2. What is the original buffer replacement policy/algorithm for PostgreSQL? In which file? In which function? From which line to which line? (4 pts)

3. Which part of PostgreSQL code defines the concept "buffer"? In which file? By which class? (2 pts)

4. Where does PostgreSQL "initialize" each buffer? In which file? In which function? (2 pts)

5. Where does PostgreSQL "use" each buffer? In which file? In which function? (2 pts)

## Submitting and Grading
This work is due on Mar. 29, about half way through the whole lab. Only **one** submission is needed for each group. 

You will get all 15 points if you answer all the questions, regardless their correctness. 

The TA will not give you the correct answer. Instead, the TA will give you correct/wrong feedback. Again, the major goal of the lab is to train your ability to work on (hack into) a real DBMS system, so the TA is not allowed to help you in navigating the source code. 