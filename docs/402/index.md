# CMPUT 402

## Topics

- [ ] first lecture
  - software quality
  - definitions
    - mccall
    - boehm
    - 25010
- [x] black box testing
  - test values
    - boundary value testing
    - boundary value analysis
    - robustness testing
    - partition testing
  - finite state machines
  - fuzz testing
- [x] white box testing
  - statement coverage
  - control flow graphs
  - branch coverage
  - "subsume"
  - condition coverage
  - branch and condition coverage
  - (MC/DC) modified conditoin/decision coverage
  - path coverage
  - data-flow coverage
  - mutation testing
  - test oracle
- [x] tdd
  - red-green-refactor
  - benefits
- [x] code review
  - code review
  - inspections
  - walk through
- [x] testing distributed systems
  - Reliability measures
  - robustness
  - testing distributed systems
    - stubs
    - mocks
    - fakes
  - chaos engineering
    - challenges
    - purpose
- [x] test smells

  - test code duplication
  - test logic in production
  - erratic tests
  - obscure tests
  - assertion roulette
  - condition logic in test
  - slow tests
  - mystery guest
  - resource optimism
  - test run war
  - general fixture
  - lazy test
  - indirect test
  - sensitive equality

  ## Summary

  - [x] black box testing
  - [x] white box testing
  - [x] tdd
  - [x] code review
  - [x] testing distributed systems
  - [x] test smells
  - [8] software quality
  - [x] intro to software quality

## Topics For Midterm 2

- [x] Measurement
- [x] DevOps
- [x] Static Analysis
- [x] Design Quality
- [x] Performance
- [x] Security
- [ ] Technical Debt

- Measurement
  - maintainability index
  - halstead volume
  - cyclomatic complexity
  - measurement
  - develop a measure
    - goal question metric
  - measurement scales
  - measurement validation
  - problems
    - correlations
    - confounding variables
- Devops
  - Goals
  - CI
  - Continuous Delivery
  - Continuous Deployment
  - Costs
  - Tools
  - Config Management
  - Monitoring
  - A/B Testing
  - Release Management
  - Feature flags
  - Prod tests
- Static Analysis
  - dynamic verification vs static verification
    - pro / con
  - for any interesting property Pr...
  - types
    - control-flow analysis
    - data-flow analysis
    - typestate analysis
    - type checking
  - IRs
  - data flow
    - constant prop
    - taint analysis
  - trade offs
    - inter vs intra
    - context sensitivty
    - aliasing
  - tools
- Design Quality
  - maintainability & design quality
    - analysis
    - SQALE
  - design principles
    - design for change
    - design for reuse
      - coupling
      - cohesion
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
- Security
  - info sec aspects
  - stride
    - threat modeling
    - dread
  - tools/techniques
    - fuzz testing
    - secure code review
    - security static analysis
  - secure design principles
- Technical Debt
  - cruft
  - non debt
  - types of debt
  - management
  - SQALE
  - calculating
  - non-remediation costs
