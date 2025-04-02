---
title: Performance
---

- Performance
  - KPI
  - performance testing
    - baseline testing
    - load testing
    - stress testing
    - soak testing
    - spike testing
  - process
  - profiling
  - code review

## Performance KPIs

### Service-oriented

#### Availability

Making sure the application is up and running, and available to users.

#### Response Time

How long it takes the application to respond to a user request.

### Efficiency-oriented

#### Throughput

Number of events that can be processed in a given time.

#### Capacity Utilization

How much of a resource is being used.

## Performance Tests

### Baseline Testing

Tests that get a baseline idea of how the system performs under normal conditions.

### Load Testing

Applying heavier loads to the system to see how it performs.

### Stress Testing

Applying loads to the system that are heavier than what it can handle. Tends to
be about searching for the limit or range in which things come apart.

May also include extended testing for robustness and ability to recover from error.

### Soak Testing

Long term testing.

### Spike Testing

Applying sudden spikes of load.

## Process

1. Decide on the testing environment.
   - may want to model after production, or consider the meaning of the tests
     if conducted in a sub-production environment.
2. Identify performance metrics.
   - decide which of the KPIs you want to investigate.
3. Plan and design performance tests (considering different user types, data, scenarios, etc.).
   - check an endpoint
   - build a flow. log in, find something, add to cart, check out.
4. Configure the test environment.
   - automate set up and teardown
5. Implement the tests.
6. Execute the tests.
7. Analyze results, report findings, and retest as needed.
   - may not have clear pass/fail findings and may need further analysis to
     determine the meaning of the results.

## Profiling

We can collect additional information during runtime to help analyze the
performance of a program including the amount of time spent in certain
classes/methods/functions, and the number of instances of classes that are
created.

## Performance Code Review

The team can have an eye on performance during code review to look out for
common performance problems:

- inefficient algorithms
- slow data structures
- bad cachine techniques
- missed parallelism opportunities
