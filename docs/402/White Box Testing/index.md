---
title: White Box Testing
---
## Coverage subsummation

** INCLUDE DIAGRAM **

## Statement coverage

Statement coverage is defined as the number of tested lines divided by the tota
number of lines in the code. 

$$
\text{Coverage} = \frac{\text{Number of tested lines}}{\text{Total number of lines}}
$$

Statement coverage will not account for branching logic, and it will not test
the inner workings of conditional statements. It's the most primitive form of
coverage. 

## Branch coverage

Branch coverage is defined as the number of branches that have been tested 
divided by the total number of branches in the code.

$$
\text{Coverage} = \frac{\text{Number of tested branches}}{\text{Total number of branches}}
$$

Branch coverage subsumes statement coverage. 

## Condition coverage

Condition coverage involves testing each condition individually to a true and
false state. 

$$
\text{Coverage} = \frac{\text{Number of boolean states tested for each condition}}{\text{Total number of conditions} * 2}
$$

Since they are varied separately, the whole impact on the predicate is not 
fully tested. Because of this, condition coverage **does not** subsume branch
coverage, or statement coverage. 

For example,

```typescript
if (a === 42 && b === 42) {
  // true
} else {
  // false
}
```

We can apply full condition coverage with test cases of:
-  `a = 42`, `b != 42`
-  `a != 42`, `b = 42`

This will test each condition in the predicate, but it will not test the
combination of the conditions. Further, it won't provide branch coverage as both
test cases resolve to a false predicate.

## Branch and Condition coverage (Decision coverage)

This basically combines condition coverage and branch coverage. Define enough
test cases so that each condition has been tested to both true and false, and
each branch has been tested.

## Modified Condition/Decision Coverage (MC/DC)

This is a variation on condition coverage where we test important combinations
of the conditions so that the whole predicate is tested. There is a weak form
and a strong form of MC/DC. 

The algorithm for MC/DC is as follows:

1. Sketch out a truth table with all the conditions and the outcomes.
2. For each condition, vary it while holding the others constant, and inspect
  the outcome where it varies from true to false.
3. Note the outcomes where it swaps from T to F.
4. Repeat for each condition.

You need `N + 1` test cases to test `N` conditions.

MC/DC subsumes branch and condition coverage, condition coverage branch 
coverage, and statement coverage. 

### Multiple Condition Coverage

A theoretical variant of MC/DC where interdependent reactions betweenconditions
are tested.

## Path Coverage

Path coverage is about walking through all possible paths in the code. At first,
glance it doesn't seem to extensive, but the complexities of looping code make
it very difficult to achieve. For example, a loop with a termination condition
of i <= 20 will have 21 paths to test. Add branching logic, and inner loops, and
the number of paths to test can grow exponentially.

## Mutation Testing

Mutation testing introduces subtle errors in the production logic. If the 
mutants have different test outcomes, then the mutants were removed. If the
mutants have the same test outcomes, then the mutant survived. You need to 
refactor or add additional tests to remove the mutant. 

$$
\text{Mutation score} = \frac{\text{Number of mutants killed}}{\text{Total number of mutants}}
$$

Some mutatations are:
- conditional boundarys: changing equality operators
- void method call: removes an invocation of a void method
- negation: negate any numeric variable 