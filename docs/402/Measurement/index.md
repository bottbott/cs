---
## title: Measurement
---

Measurements provide ideas about the current state of quality in a system, and
can help inform decisions about investing more or less in quality.

However, it's not always easy to measure, and the measurements may not be as
objective as we would like.

## Measurement

What is this dang thing?

Info and data go in, and a number comes out. This number reflects some aspect of
the system.

### Why do we care?

Helps us to:

- fund the project by understanding resourcing to deliver our desired quality.
- conduct more testing when we have identified a weakness in our robustness.
- focus on performance when we the system isn't fast enough.

### Building measures

- Decide on the measure. (what thing to measure)
- Operationalize the measure (figure out how to measure the thing)
- Implement the measure (measure the thing)
- Validate the measure (are we measuring the right thing)

#### Goal Question Metric

This is an algorithm for finding things to measure based on goals -> questions ->
metrics.

Goals and questions provide a kind of parent/child way of distilling some more
granular questions from the bigger level goals. From the question, we can
find metrics that can be used to measure the question. Goals may share questions
and questions may share metrics.

#### Operationalize & Implement

This is usually automated and may be a part of the CI process.

#### Validate

Different types of measures to have to validate:

- quantitative
  - ratio: size, time, cost
  - interval: termpature, marks,
- qualitative
  - ordinal: complexity classes
  - nominal: feature availability

Construct validity: are we measuring what we intended to measure?
Predictive validity: can the measure tell us something about some other measure?
External validity: can we generalize the measure to other systems?

#### Problems

Correlation
Confounding variables

## Maintainability Indices

These are proprietary ways of calculating how maintainable a project.

$$ MI = MAX(0, (171 - 5.2 \times \log*{10}(HalsteadVolume) - 0.23 \times CyclomaticComplexity - 16.2 \times \log*{10}(LOC)) \* 100 / 171) $$

These measures are dated and based on older studies, so their relevance may be
out of touch.

### Halstead Volume

This attempts to approximate the size and complexity of the program.

$$ Halstead Volume = Num of Operators + Num of Operands \times \log_2(Distinct(Num of Operators + Num of Operands)) $$

### Cyclomatic Complexity

Cyclomatic complexity gives a measure of the number of independent paths through
a program.

$$ Cyclomatic Complexity = edges - nodes + 2 \* endpoints $$
