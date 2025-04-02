---
title: Technical Debt
---

-
- Technical Debt
  - cruft
  - non debt
  - types of debt
  - management
  - SQALE
  - calculating
  - non-remediation costs

While building a project and satisfying the functional requirements, we may have
let things slide on the non-functional side. This accruing mass of is referred
to as technical debt.

Technical debt tends to have a multiplicate effect on efforts to remediate it,
the longer that it is put off.

Future development can also be impacted by technical debt, as poorly constructed
systems may take longer to build a feature in versus a well-constructed system.

The feature backlog, or anything else that you want to extend the system with
are not considered techncial debt.

Some debt is intentional when a compromise is made to save on time or money, but
some debt is unintentional when we perform unknowingly low quality work.

## How to manage this dang debt?

### SQALE Model

Pairs up the quality values we know and love with some metrics.

SCALE really likes this stack and supposes that each one builds on the other.

```
Reusability
-----------------
    Portability
---------------------
        Maintainability
-------------------------
            Security
-----------------------------
                Usability
---------------------------------
                    Efficiency
-------------------------------------
                        Changeability
-----------------------------------------
                            Reliability
---------------------------------------------
                                Testability
```

Each of this quality characteristics may have many sub-characteristics which
can have a requirement upon the source code to be measured.

We typically focus on remediation costs for things that we know how to fix.
Trying to calculate non-remediation, which is basically the future cost of not
fixing it now, is much harder to calculate (and kind of the more interesting
dimension).

### Sonar

SonarQube gives you remediation costs for technical debt.
