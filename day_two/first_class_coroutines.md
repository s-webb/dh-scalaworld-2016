### First-Class Coroutines for Scala - Aleksandar Prokopec

Aleksandar started by presenting a thorough explanation of behaviour trees (as used in Halo to model behaviour of AI 
opponents) and then showed how execution of a program (where the AST is analogous to a behaviour tree) can be thought
of in the same way. Under this conceptual model, a routine that calls another routine fulfils the same role as the
master loop of a computer game examining a node in a behaviour tree. If the call is implemented as a subroutine, as is
the norm, then the caller cedes control to the subroutine and resumes when it has completed. Implementing the call as
a coroutine instead allows for interaction (variable passing, flow of control) between the caller and callee.

Ok, it's not really a concept I can easily distil down into a couple of sentences. Take a look at the slides.

Anyway, the approach is interesting because it allows for concurrent and event-driven code to be implemented in a 
direct programming style (i.e. as if single-threaded), as opposed to using callbacks or monadic composition. Think
async/await vs scala.concurrent.Future.

**Slides** - http://axel22.github.io/slides/coroutines.html#/

**Repo** - https://github.com/storm-enroute/coroutines

Abstract:

> In today's era of distributed computing, reactivity and asynchronous, event-driven systems, computations must often wait until specific conditions are fulfilled. These conditions range from anything from an arrival of a network request or a keyboard stroke, to an external sensor triggering an event. The ability to suspend computations awaiting such events is more important than ever. Commonly, computations are suspended either by blocking the current execution thread, or by registering callbacks. The former has a negative impact on performance, and is typically shunned upon. The latter, which is an established practice today, comes with its own set of unpleasant syntactic overheads. Previous approaches to reduce these syntactic overheads were too focused at specific use-cases, and were not sufficiently general.
> 
> In this talk, I show that it is possible to have the best of both worlds - to write direct-style, seemingly blocking programs, but use callbacks under-the-hood to improve program scalability and throughput. I will present first-class type-safe coroutines implemented in Scala, and show how they are used to implement more specific computation models, such as Async-Await, Erlang-style actors, and Esterel-style pause statements. I continue to show that coroutines are applicable to more easily implementing collection iterators, and allow more concise ScalaCheck-style testing. Finally, I show that Scala coroutines are equivalent to continuations in expressive power.

