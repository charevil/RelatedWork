---
layout: note
title: Symbolic execution
wiki: https://en.wikipedia.org/wiki/Symbolic_execution
notes:
- bounded model checking
- fuzz testing
- separation logic
- symbolic evaluation
- symbolic execution
- DART verifier
- KLEE verifier
- SAGE verifier
- Smallfoot verifier
- VeriFast verifier
papers:
- nelson:sosp:2019
- bornholt:oopsla:2018
- baldoni:compsurv:2018
- avgerinos:icse:2014
---

Following the terminology in section 3.1 of
[bornholt:oopsla:2018], [symbolic execution] is a form of
[symbolic evaluation] where a single path is followed at a time.

Following a single path has the advantage that states do not need to be merged
at join points and so many calculations involve concrete values and so can be
evaluated directly and efficiently.  The price paid for this advantage is that
there can be an exponential number of paths.

See also [bounded model checking] and [symbolic evaluation].

Types of symbolic execution include

- (Pure) symbolic execution enumerates paths, collects path conditions
  along those paths and then checks which path conditions are satisfiable.
  (Checking path conditions can be done eagerly to prune infeasible paths
  early.)

  I think this is mostly used in [separation logic] checkers such as
  the [Smallfoot verifier] and the [VeriFast verifier].

- Dynamic Symbolic Execution (DSE) mixes concrete and symbolic execution
  benefiting from the efficiency and decidability of concrete execution and the
  need to use concrete values when interacting with the program environment
  (libraries, OS, etc.) and from the stronger guarantees of symbolic execution.

  - "Offline" DSE (aka "concolic execution") relies on concrete execution
    to drive symbolic execution using an instrumented interpreter/
    simulator/... to build symbolic representations while executing
    with concrete values.

    Used in the [DART verifier].

  - "Online" DSE (aka "Execution Generated Testing" (EGT))
    mixes concrete and symbolic execution
    by using concrete execution whenever the inputs to an operation
    are concrete and using symbolic execution if any inputs are symbolic.

    Used in the [KLEE verifier].

- Static Symbolic Execution (SSE) avoids path explosion by generating
  a symbolic formula representing all paths through a piece of code.
  It does this by merging formulae at join points in a pre-execution pass.

  This approach has significant overlap with [bounded model checking]
  and the term is mostly used in the context of hybrid approaches
  such as [avgerinos:icse:2014].

- Selective Symbolic Execution (SSE)
  interleaves concrete and symbolic execution with a focus on
  performing symbolic execution as much of the code you
  care about as possible.

  (I think this may be a special case of DSE?)

todo: it is probably less useful to have a tree-shaped taxonomy of this topic
than to have a list of design choices that define an N-dimensional taxonomy
where most dimensions include "yes", "no" and "hybrid" on their axis.  This
would better capture how thoroughly the symbolic execution design space has
been explored.

{% include links.html %}
