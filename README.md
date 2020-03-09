# A-Star-Algorithm-Application-on-Problem-Statement
Rat - Maze Problem

Purpose:
    The program defined in main.py executes A* search on an input matrix to find the shortest path from
    the upper left corner of the matrix to the bottom right (if such a path exists). The input matrix is
    read from an input file (where the first line contains the
    matrix's dimensions and subsequent lines represent the rows of the matrix). The output will be either
    "No Solution" or the cell numbers along a shortest path from the initial state to the goal state
    separated by spaces.

Structure of solution:

    Class Maze - reads the input file and stores the contents of the matrix as well as its dimensions;
        also contains a function to determine whether a particular cell is blocked.
        
    Class Queue - stores the queue of nodes to be explored; pop function returns the node in the queue
        with the lowest f(node) = g(node) + h(node) and removes it from the queue.
        
    Class Solver - initialized with an object of class Maze; has 3 member functions: solve, solution,
        and trace_path. Function solve conducts the A* search on the maze and returns a Node object if
        a solution exists or None if there is no solution. Function solution returns the string which is
        to be written to the output file ('No Solution' or a shortest path to goal). Function trace_path
        takes a goal state node as an argument and constructs the solution string by following the nodes's
        parent attributes backwards until the intial state is reached.
        
    Misc.- file also contains utility functions for determining whether a pair of coordinates
        are valid for a given maze (in_range), calculating cell number from x and y coordinates (cell_number),
        and calculating manhattan distance (manhattan_distance) as well as the definition of class Node,
        which is used in Solver.solve()to conduct A* search.
        
    main - extracts input and output file names from commandline arguments, instantiates an object of
        class Maze using the input file name, then instantiates an object of class Solver using the
        resulting Maze object. The program then calls the Solver.solution() function and writes the result
        to an output file using the name provided in the arguments.

Executing the program:
    In order to execute the program, place the main.py file and any necessary input files in the desired
    directory then open the console/terminal, navigate to the chosen directory, and use the following command:
        python main.py <input file name> <output file name>
    ex:
        python main.py input1.txt output1.txt
    The result will be written to the file name provided in the command line arguments.

