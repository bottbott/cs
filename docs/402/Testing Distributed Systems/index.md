---
title: Testing Distributed Systems
---

## Reliability measures

We define several metrics for reliability to understand our system reliability.

### Mean Time to Failure (MTTF)

This stat is the least relevant to distributed systems because for the most part
we can repair it and return it to service. It is more meant for systems that
have a single lifetime. We sum those lifetimes and divide by the number of
systems.

$$
\text{MTTF} = \frac{\sum \text{Lifetime}}{\text{Number of Systems}}
$$

### Mean Time Between Failures (MTBF)

This is the average time between failures. It is the sum of the total 
operational time less the downtime divided by the number of failures.

$$
\text{MTBF} = \frac{\text{Total Operational Time} - \text{Downtime}}{\text{Number of Failures}}
$$


### Mean Time to Recover (MTTR)

Average time that the repairs take.

### Mean Time To Resolve (MTTR)

Average time to fix and make sure it never happens again. 

## Robustness

How systems fail is very important. If we take a system like an elevator, when 
it fails we want to ensure that the system has measures to prevent a 
catastrophy, and can hopefully recover from the failure. 

In a way, this sets up stages of failiure where we can provide degraded service
rather than no service at all. 

## Testing Dependent Systems

Coupled systems are hard to test because they rely on each other. We can make
some tests that exercise large chunks of the system but those integration or
system tests take much longer to run. 

We can get some ideas about how things would work together by simulating some
part of the system.

### Test Doubles

We use alternatives to the real thing where they are unavailable, expensive,
opaque, or non-deterministic. 

#### Stubs (data)

Provides some fake data that represents what a real provider would give us.

#### Mocks (behaviour)

Begins as a blank copy of some kind of object and we configure it to behave
in certain ways. 

#### Fakes (data/behaviour)

Like a mock but with some real implementation. Provides some part of a real
interface that it is faking, but does so through some simplified means.

## Chaos Engineering

It's difficult to design test cases that can properly provide info that your
system is robust - you may need to be playing with real world conditions to
understand how your system performs. Testing up to this point has been 
conducted in a controlled environment with unit, integration and system tests,
but how will it perform in a live scenario?

### Things that we might explore

- Human error
- Bottleneck 
- Networking issues
- Hardware failure
- Resource exhaustion
- Improper configuration
- Environmental issues

### Challenges

These experiments are likely to run in production. A main concern is minimizing
impact to operations so that we can conduct the experiment without sacrificing
the whole system.

- A/B testing
- Canary deployment

### Purpose
