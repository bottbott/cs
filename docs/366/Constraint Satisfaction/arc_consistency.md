We use arc consistency in constraint satisfaction problems to be able to reduce
the domain of the variables. This can be applied in backtracking algorithm
before it runs, or while it runs. 

The problem can be pre-processed to make the problem arc-consistent before
running backtracking. You can also run AC3 or forward checking while in the
backtracking algorithm as you check each of the domain values. This step is
usually called inference. 

Forward checking only checks the neighbours of the currently selected variable,
whereas AC3 will check all the variables in the problem. 

## MAC (Maintaining Arc Consistency) (AC3 Algorithm applied in backtracking)


## Forward Checking