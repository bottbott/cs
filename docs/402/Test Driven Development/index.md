---
title: Test Driven Development
---

Changes the paradigm from direct implementation to preparing tests before 
the implementation code. 

- [ ] Red-Green-Refactor
    - Write a failing test
    - Write the minimum amount of code to pass the test
    - Refactor the code

Since there is no implementation to write tests for, the only thing that we
can use to write the tests is the requirements. This means our TDD test writing
process may more closely align with the requirements than writing tests in a
white box manner where we have intimate knowledge of the code. 

Writing a test first, gives us a client of that code. It gives us an idea of
how we'll need to interact with the code to be able to use it. It gives us
documentation of how to do that. What it takes to provide pre-conditions before
you can use your class or method. 

You get faster feedback with each testing cycle rather than writing a large
chunk of untested code and testing it at the end.

You'll have to think about coupling because it may be difficult for you to test
your class if it depends on too much which may be a hint to refactor.

## What does the research say?

Mixed. Some studies show that TDD can give code with less defects, and less time
spend debugging. Other studies show no difference in code quality.

Benefit may not result from the tests themselves, but the process surrounding
writing the tests - a slow, methodical approach to converting requirements into
code.