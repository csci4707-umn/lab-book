# Lab 2

> <i class="trigger fa fa-exclamation-triangle fa-lg"></i>
> Do **NOT** post your project on a public Github repository.

## Introduction
You are going to change the buffer replacement policy that is currently used in PostgreSQL. In particular, the original replacement policy of PostgreSQL is a "clock sweep" algorithm with LRU (Least Recently Used). In this lab, you are asked to implement an **MRU** (Most Recently Used) replacement policy without using the "clock sweep" algorithm.

## Outline
In this lab, you need to:
1. Set up PostgreSQL: Same as in Lab 1. If you correctly set up PostgreSQL in Lab1, you are safe to skip this section. See [Chapter 3](./setup.md) if you need to re-install. 
2. **(Due Mar 29)** Understand MRU, go through the related code and answer the questions. See [5.1](./lab2-0.md).
3. Implement MRU within PostgreSQL. See [5.2](./lab2-1.md).
4. Compile and test your changes. See [5.3](./lab2-2.md).

## Grading
- 15 Points **(Due Mar 29)**: Answer the questions on Gradescope. See [5.1](./lab2-0.md) for grading detail. 
- 20 Points: Your changes must be able to compile without any errors.
- 35 Points: The MRU replacement policy including incorporating the printing instructions.
- 30 Points: The quality of your solution.txt.

## Note
Since reading and understanding an open-source framework is the main goal of the lab, the TA is only allowed to do the following: 
- Help you with the installation of PostgreSQL. 
- Help you in understanding the concept of buffer management policy. 
- Help you in understanding what the assignment wants you to do. 

Unfortunately, the TA is not allowed to help you in navigating the source code (including telling you the functionality of a function or variables) since one of the goals of the lab is to make sure that you understand the source code of the buffer manager in PostgreSQL. Once you understand the source code and know where to make the change, it is very easy to solve the lab.