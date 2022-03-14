# Submit Guidance

> <i class="trigger fa fa-exclamation-triangle fa-lg"></i>
> Do **NOT** post your project on a public Github repository.

Remember this lab has **two** dues:
- Phase 1 (Due Mar. 29): Answer the questions on Gradescope.
- Phase 2 (Due Apr. 14): Submit you implementation. There will be a 10% penalty off your grade for a 24-hour late submission.


## Phase 1 submission
See [5.1](./lab2-0.md#submitting-and-grading)

## Phase 2 submission
**Only one** submission is needed for group work. 

You must submit a zip file named `<x.500>.zip`. Your zip file should unzip to a following structure:

```
<x.500>/
├── solution.txt
└── changes
    ├── foo.c
    ├── bar.c
    ├── ...
    └── foo.h
```

1. `changes`: A folder that contains all files that you have changed in order to fulfill the lab. Please only submit the file itself (don’t include the directory). For example: if you change a file in `src/backend/foo.c`, only put `foo.c` in the folder.
2. `solution.txt`: Modify the solution.txt template below as per your changes. List all group members at the very beginning of this file. 

```
Students:
1. <Student 1 Full Name> (<Student 1 x500>)
2. <Student 2 Full Name> (<Student 2 x500>)
2. <Student 3 Full Name> (<Student 3 x500>)

Brief Summary:
<A Brief Summary about the change you make (1 Paragraph max)>

Detailed Changes:
1. <Modified File 1>: <The path of the modified file from src directory>
	- <Detailed changes of the file>.
	For example: In line xxx, I make a change so that the buffer will do ......
	
2. <Modified File 2>: <Path from src>
	- <Detailed changes of the file>.
```

Each violation to the submission guideline will result in a **10%** penalty.
