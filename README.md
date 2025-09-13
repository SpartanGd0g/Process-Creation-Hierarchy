# Process-Creation-Hierarchy
To simulate process creation and destruction when implemented with linked lists

-------------------------------------------------------------------------------------

Specification:
The program creates/destroys child processes based on choosing from a menu of choices, where
each choice calls the appropriate procedure, where the choices are:
1) Initialize process hierarchy
2) Create a new child process
3) Destroy all descendants of a parent process
4) Quit program and free memory

Assignment:

• Create a process creation hierarchy as an array of length MAX_PROCESSES which references
process control blocks (PCBs), indexed 0 to MAX_PROCESSES-1.
• Each PCB is a structure consisting of two fields:
o parent: a PCB index corresponding to the process’ creator
o children: a pointer to a linked list, where each node contains the PCB index of one child
process and a link to the next child in the linked list
• The necessary functions are simplified as follows:
o create_child() represents the create function, which prompts for the parent process p.
The function creates a new child process q of process p by performing the following

tasks:

▪ allocate memory for an unused PCB[q]
▪ record the parent's index, p, in PCB[q]
▪ initialize the list of children of PCB[q] as empty (NULL)
▪ create a new link containing the child's index q and append the link to the
children field of PCB[p]
o destroy_descendants() represents the destroy function, which prompts for the parent
process p. The function recursively destroys all descendent processes (child, grandchild,
etc.) of process p by performing the following tasks: for each element q on the linked list
of children of p:
▪ destroy_desecndants(q) (recursively destroy all descendants of q)
▪ free memory utilized by PCB[q] and set it to NULL
▪ Free memory utilized by the node with id q and set it to NULL
What NOT to do:
• Do NOT modify the choice values (1,2,3,4) or input characters and then try to convert them to
integers--the test script used for grading your assignment will not work correctly.
• Do NOT turn in an alternate version of the assignment downloaded from the Internet (coursehero,
chegg, reddit, github, ChatGPT, etc.) or submitted from you or another student from a previous
semester—the test cases from this semester will not work on a previous semester’s assignment.
• Do NOT turn in your assignment coded in another programming language (C++, C#, Java).
What to turn in:
• The source code as a C file uploaded to Canvas by the deadline of 11:59pm PST (-20% per
consecutive day for late submissions, up to the 4th day—note 1 minute late counts as a day late, 1
day and 1 minute late counts as 2 days late, etc.)
• As a note, even though your code may compile on a compiler you have installed on your
computer, I do not have access to your computer. I will be using the following free online
compiler for testing, so make sure your code compiles with the following online C compiler
before submitting: https://www.onlinegdb.com/online_c_compiler
If it does not compile with the above compiler, the default grade is 0 points since I cannot run it.
