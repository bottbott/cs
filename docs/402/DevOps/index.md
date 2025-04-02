---
title: DevOps
---

- DevOps
  - [x] Goals
  - [x] CI
  - [x] Continuous Delivery
  - [x] Continuous Deployment
  - [ ] Costs
  - [ ] Tools
  - [x] Config Management
  - [x] Monitoring
  - [x] A/B Testing
  - [ ] Release Management
  - [x] Feature flags
  - [x] Prod tests

DevOps includes all of the work after the code is written. Once it needs to
enter the CI pipeline or the CD pipeline - or both! DevOps helps to make things
easier between developers and infrastructure. Has a focus on automation,
scaling, monitoring, and pipelining.

## Continuous Integration (CI)

Basically automated building and testing of the code. Let's you know if after
any commit there is an issue in the code, but it relies on having good
static or dynamic tests in place. Helps you to get more feedback on failures
or errors in the system and give some confidence around robustness of the code.

## Continuous Delivery & Continuous Deployment

CDel gets the code ready to be deployed, but does not deploy it. CDep does
deploy the code.

It takes a lot of tooling and work to get CD to work, and cost to support the
infrastructure to home the deployments, but you get constant feedback on
knowing that the code will work. The feedback leads to general faster agility
on releases where you don't have to wait for a release cycle to complete before
learning about any issues.

## Infrastructure Configuration Management

Infrastructure as code is an approach to script the creation of infrastructure
projects. In CMPUT 402, this was most closely reflected by the use of Docker
and Github Actions.

## Monitoring

Monitoring is very important to help support quality objectives for robustness,
reliability, performance and security. Clues can exist in the system logs that
enable developers to see what has happened when it is not easy or possible to
debug a running process, or when things happen in production or outside
working hours.

## A/B Testing

This is typically an approach used to expose different versions of the system
to different audiences. It's probably more closely related to chaos engineering
than testing, because it's usually an experiment to collect some kind of measure
to then decide which version to use.

### Feature Flags

Feature flags can also be an easy way to enable A/B testing because you can
program in the ability to easily enable or disable features on the fly.

## Release Management

### Major/Minor/Patch

Major releases introduce breaking changes to the API. Minor releases add
features that must be backwards compatible without breaking the API. Patches are
compatible bug fixes.

## Testing in Prod

Beta tests, AB Tests, tests across devices/regions

It's important to collect real world information on real world systems using
real world data. There are blind spots when we are only in test environments and
using staged data.

There's a bigger focus on monitoring here since production shouldn't be stopped
and interfering with the process through debugging may not be possible, or may
put the system at unreasonable risk.
