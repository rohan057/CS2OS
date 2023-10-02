# CS2OS

Part 1: Containers, scripting and UNIX CLIs:
The container provided for this assessment uses the bash shell, and includes an executable named “trial”.
Write a “for” loop in bash script that runs the program “trial” 20 times and sends its output to a differently
named file each time. Have the script name the output files output NN.txt, where NN is 01,02,...,20 [10
marks], and also print out the name of the current file so the user can see the progress of the script.

Part 2: Programming Linux with C:
Write a program that copies the first 256 bytes from the file “input.txt” to the file “output.txt”, using the
Linux system call interface.
The syscall() function is the lowest level of function generally available through the kernel API.
Above this, there are its wrapper functions, e.g. open(), read(), and so on. Your task is to implement
the file copy using both syscall() and the wrappers. Your code should determine which method to use
based on the value of the first command-line argument given to your program; if ‘s’ then use
syscall() and if ‘w’ then use the wrapper functions.

Part 3: Synchronisation and threads:
The final section is a version of the “producer–consumer problem”. The program creates a variable number
of threads (2 ≤ N < 1024) based on command-line parameters, and threads either produce or consume
data. They share a circular buffer to communicate these data to each other. If there are many producers,
the buffer fills up and the producers have to wait to insert data. Conversely, if there are many consumers,
the buffer can become empty and the consumers have to wait. If access to the buffer is not properly
synchronised, data can be lost.
Your task is to take the given source code file “prod-com.c” and fill in the sections marked TODO (the
functions insert item and remove item), to make the program work effectively. The necessary
variables for the semaphores and mutex are already provided and initialised in the sample code: empty
and full semaphores which count the number of empty and full slots in the buffer, and mutex, which
is a binary semaphore that protects the actual insertion and removal of items in the buffer. Hint: this
problem is taken from the Silberschatz text book, at the end of Chapter 6. You will need to use pointers,
so make sure you are clear about how pointers are written in C, how “pointer arithmetic” works to move
through sequential items in memory, and how to “dereference” a pointer to access or write to the memory
location that it points to. Note that you must access the buffer using pointer dereferencing, not using array
indexing (i.e. without using the buffer[i] syntax). See Figure 1 for the example output of a correct
solution.
