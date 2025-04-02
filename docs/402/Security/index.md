---
title: Security
---

## Information Security Aspects

- Confidentiality
  - make sure that other people can't see stuff they shouldn't see.
- Integrity
  - make sure that data is what it's supposed to be and hasn't been tampered with.
- Availability
  - users can get the data
- Authentication
  - make sure you know who is who. don't confuse someone for anyone else.
- Non-repudiation
  - make sure you know who did what.
- Authorization
  - make sure users can only do what they are supposed to be able to do.

## Microsoft Security Practices

1. Train employees

- people are huge attack surface. make sure they have appropriate training.

2. Define Security Requirements

- evalute the combination of security aspects and business requirements to
  decide what your security requirements will be.

3. Define Metrics & Compliance Reporting

- figure out how to define priorities.
- set up compliance rules around actions to take
  - e.g. all critical bugs must be fixed in 8 hours.

4. Perform Threat Modeling

- brainstorming security problems, triaging, and plans
- Microsoft follows their STRIDE process for this process.

5. Establish Design Requirements

- how to deal with cryptography
- how to deal with authentication
- how to deal with authorization
- how to deal with logging

6. Define and Use Cryptography Standards

- pick a standard that meets your needs. choosing a weak standard will
  be catastrophic.

7. Manage the Security Risk of Using Third-Party Components

- third party components are another attack surface. checks for vulnerabilities
  and keep things up to date.

8. Use Approved Tools

- unapproved tools are an attack surface

9. Perform Static Analysis Security Testing (SAST)

- linting for security problems
- follow secure coding standards
- security code review

10. Perform Dynamic Analysis Security Testing (DAST)

- fuzz testing

11. Perform Penetration Testing

- have third party testers try to break the system.

12. Establish a Standard Incident Response Process

- emergency response plan.

## STRIDE

Microsoft's own threat modeling process reviews several different threats.

(S)poofing, (T)ampering, (R)epudiation, (I)nformation Disclosure,
(D)enial of Service, (E)levation of Privilege

- Spoofing: trying to impersonate someone else. (attack on authentication)
- Tampering: trying to change data (attack on integrity)
- Repudiation: trying to deny that you did something (attack on non-repudiation)
- Information Disclosure: trying to get information you shouldn't have (attack on
  confidentiality)
- Denial of Service: trying to make a service unavailable (attack on
  availability)
- Elevation of Privilege: trying to get access to something you shouldn't have
  (attack on authorization)

STRIDE threat modeling uses a five step process to discover threats,

1. Identify Security Objectives
   - brainstorm what you must protect, what you must comply with, what you
     must follow.
   - can think in lense of STRIDE, or in terms of the security aspects and how
     aspects of your application may be vulnerable to attacks from them.
2. Create data flow diagram
   - consider how data moves through your system
   - model as a flowchart
   - to be used as a tool to find possible threat vectors
3. Identify threats
   - make a list of threats
4. Annotate threats
   - organize threats with STRIDE category and mitigation strategy per threat.
5. Rate threats
   - determine how to rank what you should work on
   - could use high, medium, low
   - could use DREAD

## DREAD

A rating system for 5 different aspects of a threat and a value of high,
medium, or low.

- Damage potential
  - how bad will it be?
- Reproducibility
  - will it happen every time you do it?
- Exploitability
  - how easy is it to do?
- Affected users
  - how many people will be affected?
- Discoverability
  - how well known is it?

## Secure Design Principle

- Minimize Attack Surface
  - anything that an attacker can interface with
- Establish secure defaults
  - ensure that defaults are provided and are a secure choice
- Least Privilege
  - users should only have the minimum privileges necessary to do their job
- Defense in Depth
  - provide multiple layers of security
- Fail Securely
  - on failure, don't reveal anything more than necessary. give as little as
    possible.
- Separation of Duties
  - use roles to split up user groups for different types of authorizations
- Avoid Security by Obscurity
  - just hiding something won't stop someone from finding it.
- Keep Security Simple
  - a complicated security architecture is easy to introduce bugs into
- Fix root causes
  - research and fix issues at the root to ensure a proper fix
