---
title: Test Smells
---

Tests have a familiar set up.

1. Arrange (fixtures, mocks, etc.)
2. Act (run the test)
3. Assert (check the results)

Fixtures can be shared between tests for the arrange phase when there is common
setup to be performed.

## Test Code Duplication

This is a violation of DRY in test code.

## Test Logic in Production

Instead of using a test object like a stub, mock or double. The production code
is directly modified with a "feature flag" approach for testing.

## Erratic Tests

Tests should be deterministic. If the test depends on something that may not
always provide the same response, then the test may fail intermittently.

## Resource Optimism

Depending on external resources will have non-deterministic results depending on
when and where the test is executed. On a different day, at a different time. 
On a CI environment, on a local environment. 

## Obscure Tests

This is a test that is hard to understand what is going on. There may be
overwhelming complication in the arrange, act or assert stages. 

## Assertion Roulette

When it's hard to determine which assertion failed in a test. 

## Condition Logic in Test

A test should do one thing, and if there is conditional logic inside the test it
may be trying to do too much, and it may be hard to get consistent results from
a test that does things differently depending on its inputs.

## Slow Tests

These just reduce the productivity of the team.

## Mystery Guest

When we make use of test fixtures and @BeforeTest annotations, they can hide 
errors in the system because part of the work is done outside of the test.

## Test Run War

Race conditions between tests running at the same time due to parallelism, or
multiple actors executing the test suite.

## General Fixture

A fixture has been set up to be shared between tests but it does too much to try
to cover all the cases, and that means that it can take too long to set it up.

## Lazy Test

Not sure where the name comes from, but this is when there are multiple tests
that use the same fixture to test the same method.

## Indirect Testing

Test invokes another test.

## Sensitive Equality

When comparing things, we should have a very clear, reususable, and robust 
equivalence mechanism. Relying on something like `toString()` could be very
brittle since the underlying string serialization could change.