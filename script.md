# Basic Stuff about Benchmarking

## Basics
- The science part of computer science: other people are just doing maths
  - Start with a hypothesis, be very specific about what should happen
  - Do the experiment, do they match with the hypothesis?
  - Might need to re-iterate the hypothesis or fix your system (different from benchmark selection)
- What did you say your techniques are going to solve? Are they solving them?
- Even we know what does it perform on each type of thing, how does it work on *real-world* scenario/workload
- show your strength, what should happen
- show your weaknesses, what you are not covering, don't try to mislead reviewer
- extraordinary claims require extraordinary evidence
  - if something makes your system extremely good, more evidence is needed
  - if something is very obvious, you can get away with not having a benchmark for it
## Infrastructure
- deterministic
- you need to see it fail
- automated* (you will run this a *LOT* of times) (but also avoid over-engineering, be very careful what parameters you have)
- granular, fast test: debuggable
## Common pitfalls
- Scope: benchmarking the right thing
- Be aware what you are measuring: saturation
- Statistical reporting
  - geometric mean
  - when not to use mean at all
  - always variances
