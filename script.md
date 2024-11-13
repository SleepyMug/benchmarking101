# Basic Stuff about Benchmarking

## Basics
#### Even we know what does it perform on each type of thing, how does it work on *real-world* scenario/workload (BeeBox?)
#### Show your strength, what should happen.
people needs a good guess of a function: scenario -> performance
#### Show your weaknesses, what you are not covering
don't try to mislead reviewer (you'll either fail, or worse, succeed)
#### Extraordinary claims require extraordinary evidence
- if something makes your system extremely good, more evidence is needed (my system uses a single core but it's faster than a multi-threaded solution)
- if something is very obvious, you can get away with not having a benchmark for it (My system reduces local IO of a class of applications, I don't have a negative impact on network. I added additional tag to each RPC call, so my system doesn't have much memory overhead)

## Infrastructure
Some of these ties into good testing
#### Automated* 
You will run this a *LOT* of times. But also avoid over-engineering, be very careful what you are parameterizing over

Repeatable: seriously consider docker, or manage your states and dependencies **extremely** carefully (output directory cleared? are there packages you didn't put into setup scripts?)

Push-button effort: (If you can run a single command you will run it, if you need to think about what to run you won't, and it's going to take longer for you to discover problems)

What are you doing manually, why? (if you need to do three things to get a result, consider making them into one)

Separate data generation and data presentation and filter later: you want to present the data in different ways without re-running experiments

Debuggable
  - granular: don't put everything inside one script (you want to fix problem and test them on the smallest unit, don't want to run everything else (especialy the slow ones together)
  - fast: have small things you can run to catch problems

Deterministic*

You need to see it fail first: story: we did a compiler-based transformation, it turns out for weeks this guy named X was just measuring the overhead of having no optimization.

## Common pitfalls
[Benchmark crimes](https://gernot-heiser.org/benchmarking-crimes.html)

- collect results while running other things
- take forever to get your first result
- inability to attribute overheads
- Scope: benchmarking the right thing
- Be aware what you are measuring: saturation
- Statistical reporting
  - geometric mean
  - when not to use mean at all
  - always variances

#### Report results on meaningful envs
If your system is supposed to help large scale systems, don't just run it on something that fits in to your backpack

#### Understand the numbers
Don't trying random things and hope it works. Narrow down and identify problems, then solve them.

Definitely don't repeat and pick the best result.

#### Average over multiple executions
Obviously

#### Get some results first (BFS)
Iterating the end-to-end system

- Make sure your approach work as expected on your target, avoid going three months into a project then realize that your Python code
 is going to cause problem in your multi-threaded problem
- Optimize performance at the bottleneck

#### Report variances
Average don't mean much if you don't have at least standard deviation. 
High standard deviation can mean
- The improvements still be just by chance

If you have imagine you have 5 second improvement in running time, while the measurement has a 20 second standard deviation,
how many times you need to repeat the measurement before you claim the improvement is significant?

The answer is roughly 64 (within a factor of two) if you look for p < .05, but most likely system reviewers don't do this kind of calculation, 
they'd tell you your measurement is too noisy.)

- Your measurement includes too many external things
Did you include network? Do you have additional interference?


