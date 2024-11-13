# Basic Stuff about Benchmarking

## Basics
#### Realism
- System research is about things that works in the current world.
- No free lunch theorem
- X
- Representative set

#### Be Complete and Be Frank
- X
- don't try to mislead reviewer (you'll either fail, or worse, succeed)

#### What to Benchmark?


## Infrastructure
Some of these are related to good testing, because benchmarks tests our system's performance and effectiveness

#### General Setup
- Usage managed server: control---SPEC CPU sun light story; scale---laptops are tiny
- Repeatable: seriously consider docker, or manage your states and dependencies **extremely** carefully (output directory cleared? are there packages you didn't put into setup scripts?)


#### Anticipation for Problems

#### Validity
We did a compiler-based transformation, it turns out for weeks this guy named X was just measuring the overhead of having no optimization.
#### Automation
You will run this a *LOT* of times. Automate it to the point where you like running them.
But also avoid over-engineering, be very careful what you are parameterizing over

Push-button effort: (If you can run a single command you will run it, if you need to think about what to run you won't, and it's going to take longer for you to discover problems)

What are you doing manually, why? (if you need to do three things to get a result, consider making them into one)

Separate data generation and data presentation and filter later: you want to present the data in different ways without re-running experiments

## Some Points on Methodology

#### No Interference

#### Statistical Reporting
The number you repeat technically is related to the effect vs standard deviation

#### Get Some Results First

#### Other Things

- collect results while running other things
- take forever to get your first result
- inability to attribute overheads
- Scope: benchmarking the right thing
- Be aware what you are measuring: saturation
- Statistical reporting
  - geometric mean
  - when not to use mean at all
  - always variances

[Benchmark crimes](https://gernot-heiser.org/benchmarking-crimes.html)

