---
title: Design Quality
---

- Design Quality
  - maintainability & design quality
    - analysis
    - SQALE
  - design principles
    - design for change
    - design for reuse
      - coupling
      - cohesion

We can approximate the quality of the program design by examining quality
measures, performing static analysis, and analyzing the code structure to review
coupling and cohesion.

It's important that the program be well designed because it may affect the
future maintenance of the program, and the cost of adding new features.
Developers may require more time to understand poorly designed systems, or be
at risk of introducing more errors.

## Analysis

### Maintainabilty Index

The MI gives us some indication of how the system is doing in terms of the
Halstead volume (gives an idea of the size and complexity of the program),
cyclomatic complexity, and lines of code.

### SQALE (Software Quality Assessment based on Lifecycle Expectations)

This is an opinionated framework for evaluting code quality.

Takes the quality values from 25010 and derives measures to assess them.

## Design Principles

### Design for Change

We can use information hiding and encapulation to prevent our implementation
details from restricting the future changes to the system. By operating with a
strict interface, it's much easier for us to change the internal workings
without impacting the system.

We can rely on interfaces about what a thing does without having to worry about
how it does it.

### Design for Reuse

Avoid deep inheritance hierarchies. The hierarchy itself has internal coupling
between the classes, and this coupling extends to classes that use the
classes from the hierarchy. Inheritance should be used in moderation.

Alternatively, we can choose to use composition to build up the classes by
adding in what we need. We can also use delegation to rely on another object
for some of the functionality. Preferably delegating to an interface rather than
a concrete class.

### Design for robustness

### Design for testability

### Low coupling

As the graph of connections between classes increases, so does the risk of any
change to one of those classes causing a problems in some other class.

Classes must be coupled to create complex behaviour, but we want to strive for
low coupling to minimize the risk. Low coupled classes are easier to test, and
easier to reuse since there is less dependent requirements to satsify.

Some code smells of high coupling include:

- changing class X requires changes in class Y
- having direct dependencies on objects rather than interfaces

### High cohesion

Cohesion is all about whether the class is doing the same kinds of things, or
different things. A highly cohesive class will be focused on something, and a
low cohesive class will be doing a bunch of different things. A common low
cohesive smell is a god-class that just does everything.

Reducing cohesion in a class may involve grouping together methods and pulling
them into new classes. This can help improve cohesion in the existing class.
