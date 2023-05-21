# Sudoku Solver Project

The project will take in a formatted sudoku file, create a CNF file to solve it, pass it through the SAT4j solver to retrieve a solution, decode the solution, and print it out. 
The project ultilizes the transform and conquer algorithm to transform a sudoku board into a SAT problem, solve the SAT problem, and transform the SAT solution back into the solution for a sudoku board. 

## Sudoku Inputs
The sudoku files follow a format where the first two numbers are the subgrid's length and width and the remaining numbers are the board itself. The 0's seen are meant
to repesent blank squares on a board which will get filled in once the program finds the solution. 

```
Sudoku 9x9 Board Example
3
3
5 4 0 2 0 9 0 0 1
0 0 0 5 0 0 0 0 4
0 0 7 0 0 0 9 0 0
8 0 0 0 3 0 0 6 7
0 0 0 6 0 5 0 0 0
9 3 0 0 1 0 0 0 2
0 0 1 0 0 0 6 0 0
2 0 0 0 0 6 0 0 0
3 0 0 1 0 7 0 4 9
```
## Output
The program will test 6 sudoku board with sizes ranging from 4x4 to 25x25. The code will solve each board, display the solution to the board, and how long it took to
complete the boards in milliseconds. At the end the program will state how long it had took to complete all 6 boards in milliseconds. 

```
Testing: puz3
9 11 12 16 2 6 14 13 1 10 4 15 5 8 3 7 
10 6 8 14 7 9 1 16 12 2 5 3 13 11 4 15 
1 15 13 2 3 12 4 5 8 11 7 9 16 10 14 6 
5 7 3 4 11 15 8 10 16 14 6 13 1 2 12 9 
14 5 9 3 10 2 11 6 7 1 16 12 15 13 8 4 
12 1 6 10 15 4 3 9 14 5 13 8 7 16 2 11 
4 13 2 7 16 8 12 1 6 15 9 11 14 5 10 3 
16 8 11 15 13 7 5 14 4 3 10 2 12 9 6 1 
3 16 4 1 8 13 9 12 15 6 2 14 10 7 11 5 
7 12 5 9 4 16 15 2 11 8 1 10 3 6 13 14 
6 2 14 11 5 1 10 7 9 13 3 16 4 12 15 8 
13 10 15 8 14 11 6 3 5 4 12 7 2 1 9 16 
15 9 1 6 12 10 2 8 3 7 14 5 11 4 16 13 
2 4 10 5 1 3 16 11 13 9 15 6 8 14 7 12 
8 3 7 12 9 14 13 4 10 16 11 1 6 15 5 2 
11 14 16 13 6 5 7 15 2 12 8 4 9 3 1 10 
Time taken to complete: 753

Testing: puz4
18 2 22 19 9 3 14 17 8 16 15 23 5 20 6 11 25 13 4 24 10 7 1 21 12 
14 10 17 11 8 5 6 18 21 9 22 16 4 12 24 2 7 23 1 20 15 25 13 19 3 
25 15 24 13 7 20 1 23 4 12 10 11 8 3 14 21 18 16 5 19 17 22 2 6 9 
23 4 1 21 12 11 15 10 22 2 7 19 13 9 25 6 8 17 14 3 24 16 18 20 5 
3 5 16 6 20 7 25 19 24 13 1 21 17 18 2 10 12 22 9 15 11 23 14 8 4 
11 3 18 15 22 8 21 24 7 1 5 12 10 14 13 16 17 25 23 2 4 20 6 9 19 
16 9 12 25 17 4 19 22 5 10 24 2 18 21 15 3 20 6 13 1 7 14 8 23 11 
2 7 6 4 21 9 16 13 3 18 23 22 20 19 11 5 14 10 15 8 25 1 24 12 17 
19 14 23 5 1 2 20 25 11 17 8 6 7 4 16 12 9 18 24 21 22 3 10 13 15 
20 8 10 24 13 6 23 15 12 14 9 1 25 17 3 4 11 19 22 7 5 2 21 18 16 
24 19 9 1 25 23 10 5 17 4 16 3 11 6 22 18 2 20 21 13 12 15 7 14 8 
4 6 8 16 5 22 9 2 15 11 25 18 21 24 1 14 19 3 7 12 23 13 20 17 10 
10 23 2 12 11 18 7 3 14 24 17 20 15 13 19 1 22 5 8 4 6 9 25 16 21 
15 22 13 20 14 19 12 6 16 21 2 8 9 7 4 25 10 24 17 23 3 5 11 1 18 
7 18 21 17 3 25 13 1 20 8 12 5 14 23 10 9 16 15 11 6 19 24 4 2 22 
8 11 25 7 23 24 2 21 18 20 4 9 3 10 5 15 1 12 6 14 16 17 19 22 13 
1 24 5 3 10 17 4 9 23 7 13 14 6 16 18 19 21 2 25 22 8 11 12 15 20 
21 12 15 22 18 10 8 14 13 19 20 25 23 2 17 24 5 7 16 11 9 6 3 4 1 
17 20 19 14 2 15 22 16 6 5 11 7 12 1 8 13 4 9 3 10 18 21 23 24 25 
6 13 4 9 16 1 11 12 25 3 19 24 22 15 21 17 23 8 20 18 2 10 5 7 14 
22 25 7 10 4 14 24 11 19 23 21 17 16 8 12 20 3 1 2 9 13 18 15 5 6 
13 1 14 23 15 21 18 4 9 6 3 10 19 5 7 22 24 11 12 16 20 8 17 25 2 
5 16 11 8 19 13 3 20 1 25 6 4 2 22 23 7 15 21 18 17 14 12 9 10 24 
9 21 3 18 6 12 17 7 2 22 14 15 24 25 20 8 13 4 10 5 1 19 16 11 23 
12 17 20 2 24 16 5 8 10 15 18 13 1 11 9 23 6 14 19 25 21 4 22 3 7 
Time taken to complete: 1161

Testing: puz2
1 5 10 2 3 4 9 11 12 16 6 14 15 13 7 8 
14 16 8 13 5 15 7 12 4 3 1 2 9 10 6 11 
9 12 4 7 10 16 6 1 8 13 15 11 3 5 14 2 
3 6 11 15 2 13 8 14 7 5 10 9 4 16 12 1 
13 4 14 3 8 7 11 10 5 12 2 6 1 15 16 9 
8 11 7 6 4 1 2 16 9 10 14 15 12 3 5 13 
12 9 1 10 13 5 15 6 3 4 16 8 14 2 11 7 
16 15 2 5 9 12 14 3 1 11 7 13 10 6 8 4 
6 2 16 14 11 9 4 13 15 1 12 5 8 7 10 3 
7 13 9 1 15 2 3 5 11 14 8 10 16 12 4 6 
5 8 3 11 1 10 12 7 2 6 4 16 13 9 15 14 
15 10 12 4 14 6 16 8 13 9 3 7 2 11 1 5 
2 3 5 8 12 14 10 15 6 7 9 4 11 1 13 16 
10 7 13 12 16 3 5 9 14 8 11 1 6 4 2 15 
11 1 15 9 6 8 13 4 16 2 5 12 7 14 3 10 
4 14 6 16 7 11 1 2 10 15 13 3 5 8 9 12 
Time taken to complete: 150

Testing: unsolvable
Unsatisfiable (trivial)!
Time taken to complete: 25

Testing: puz1
5 4 3 2 6 9 8 7 1 
6 8 9 5 7 1 3 2 4 
1 2 7 8 4 3 9 5 6 
8 1 5 9 3 2 4 6 7 
4 7 2 6 8 5 1 9 3 
9 3 6 7 1 4 5 8 2 
7 9 1 4 2 8 6 3 5 
2 5 4 3 9 6 7 1 8 
3 6 8 1 5 7 2 4 9 
Time taken to complete: 63

Testing: smallPuz
2 3 4 1 
1 4 2 3 
3 2 1 4 
4 1 3 2 
Time taken to complete: 87

Time taken to run to completion: 2252
```


## Project Link

The project is in a private repository at the request of a professor due to it being a school project but it can be shared if requested.
If access is requested/granted, the project can be found below 

[:simple-github: Project Link](https://github.com/mtobino/DAA_Projects/tree/master/src/main/java/sudokuSolverProject){ .md-button .md-button--primary }
