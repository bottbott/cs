---
title: Static Analysis
---

- [ ] Static Analysis
  - [x] dynamic verification vs static verification
    - [x] pro / con
  - [x] for any interesting property Pr...
  - [ ] types
    - [x] control-flow analysis
    - [x] data-flow analysis
    - [x] typestate analysis
    - [x] type checking
  - [x] IRs
  - [x] data flow
    - [x] constant prop
    - [x] taint analysis
  - [x] trade offs
    - [x] inter vs intra
    - [x] context sensitivity
    - [x] aliasing
  - [ ] tools

## Dynamic vs Static

The first types of tests we looked at in the course focused on dynamic verification
where we used a live system and moved it in and out of certains states to see
what would happen to it and if it met assertions that we set.

Static analysis does not involve running the program, but instead looks at
what the code might do from examining it. This includes some previously discussed
topiocs like code reviews, walkthroughs, and inspections, but typically we are
discussing automated static analysis.

| **Static Verification Tools**                                   | **Dynamic Verification Tools**                        |
| --------------------------------------------------------------- | ----------------------------------------------------- |
| ❌ Having a precise & sound static analysis is hard/expensive   | ❌ Run-time overhead                                  |
| ✅ Relatively cheap when compared to running thousands of tests | ❌ Depends on the quality of inputs                   |
| ❌ Can have false positives                                     | ✅ Usually precise — an observed failure is a failure |
|                                                                 | ❌ Can have false negatives                           |

## Undecidability of Static Analysis

A problem with static analysis is that for anything interesting that you might
want to examine, it's impossible to write some analysis that would work for
every program. This means that we tend to approximate the analysis to make it
work.

## Code Representation

Source code is too verbose and too plain English to be able to analyze it
directly. The code must be converted into one or more intermediate
representations (IRs) that are more machine friendly for analysis.

| **High-Level IR**     | **Low-Level IR**     |
| --------------------- | -------------------- |
| language-specific     | language-independent |
| machine-independent   | machine-specific     |
| tree/graph            | instruction sequence |
| control-flow          | gotos                |
| compound expressions  | simple expressions   |
| high-level constructs | expanded constructs  |

### Abstract Syntax Tree

The code is modelled as a tree.

### 3-Address Code

This version looks a lot closer to assembly code. Three addresses is representative
of two operands and the result.

### Control Flow Graph

The code is modeled as a graph where each edge is usually some conditional
branching, and each node is a block of code or a single instruction.

## Static Analysis Types

### Control-Flow Analysis

This uses a control flow graph created from the source code or partially
compiled code and analyses all of the paths through the code.

It can't distinguish between different paths that could be exclusive under
examination. if(p) and if(!p) would clearly be exclusive, but the analysis
could not know what p will resolve to.

This can lead to some problems with false positives.

Graphs can be unsound if they don't include all paths such as those that occur
with exceptions.

### Data-Flow Analysis

Here we can analyze the flow of values through the code.

Constant propagation can be used to promote values further in the code when
there is no interceding logic that may affect the value. This could be applied
in dead code elimination to propagate a value forward to the point that it is
used in a conditional that would clearly never run it's body.

Taint analysis involves sources and sinks. Sources generate some value that
could be problematic if it arrives at a sink. We need to be sure to sanitize
values from sources before they reach sinks. This can be a common concern in
security when handling passwords, or receiving user input. A common problem
in this domain is SQL injection where user input is not properly sanitized.

Data flow analysis helps us find unused variables, uninitialized variables, and
variables reassigned before being used.

### Typestate Analysis

Checks for valid sequences of operations are made on an object.

### Type Checking

Check for mismatches in expected types.

## Trade Offs

The complexity of static analysis increases as the scope of what is being included
increases. If we analyze a singular function, then we can be very fast and precise.

If we analyze the whole program, we can see more interactions between classes,
methods, and functions, but it comes at a greater cost for the analysis.

We refer to this local view as intra-procedural analysis and the wider view as
inter-procedural analysis.

Context sensitive analysis includes temporal coupling to remember when a method was
called versus context insensitive analysis which does not remember the context of the call.

Aliasing is required to know about variable or reference renaming.
