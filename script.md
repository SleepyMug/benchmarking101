# Basic Stuff about Benchmarking

## Basics
- Even we know what does it perform on each type of thing, how does it work on *real-world* scenario/workload (BeeBox?)
- show your strength, what should happen.
people needs a good guess of a function: scenario -> performance
- show your weaknesses, what you are not covering, don't try to mislead reviewer (you'll either fail, or worse, succeed)
- extraordinary claims require extraordinary evidence
  - if something makes your system extremely good, more evidence is needed (my system uses a single core but it's faster than a multi-threaded solution)
  - if something is very obvious, you can get away with not having a benchmark for it (these completely independent workload
## Infrastructure
- automated* (you will run this a *LOT* of times) (but also avoid over-engineering, be very careful what parameters you have)
  - Repeatable: seriously consider docker, or manage your dependencies **extremely** carefully
  - Push-button effort
    - What are you doing manually, why?
  - Separate data generation and data presentation: you want to present the data in different ways without re-running experiments
- debuggable
  - granular: don't put everything inside one script
  - fast: have small things you can run to catch problems
- deterministic*
- you need to see it fail first
## Common pitfalls
- [Benchmark crimes](https://gernot-heiser.org/benchmarking-crimes.html)
- report only local results
- reporting only one execution
- collect results while running other things
- take forever to get your first result
- trying random things (or even worse, just repeating and pick the best)
- inability to attribute overheads
- Scope: benchmarking the right thing
- Be aware what you are measuring: saturation
- Statistical reporting
  - geometric mean
  - when not to use mean at all
  - always variances