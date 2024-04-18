Search tree comparisons:  (re: quiz 8)
 - 

Constraint satisfaction problems have factored states where there is additional
information available about a given state and this lets us do more than just
search blindly. We can use this information to guide our search. 

Constraint satisfaction problems are defined as:

- Variables
- Domain for the variables
- Constraints that limit the domain values for the variables (unary, binary,
  global)

One powerful concept that emerges from CSP problems is using the constraints to
minimize the search space. Constraints eliminate possible domain values for
some variables and this means the search trees branching factor is reduced.