## Main Idea
- Base case: if A is complete, return A.
- Select a variable (FA, MRV, etc)
- Loop for the domain of the variable
    - Check if the value is consistent with the constraints
    - Assign variable to the value
    - Recursively call backtracking (now has that variable assigned)
    - if it didn't fail, return the assignment

The algorithm loops over domain values and recursively explores their 
assignment. If nothing in the domain worked, it backtracks to the previous
variable and tries a different value. 

## Backjumping
Backjumping is an intelligent variation of backtracking 


## Conflict-Directed Backjumping