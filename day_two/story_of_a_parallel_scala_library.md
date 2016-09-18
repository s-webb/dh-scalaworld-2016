### The Story of a Parallel Scala Library - Vlad Ureche

Vlad Ureche, whilst working as a PhD student at EPFL under Martin Odersky, has created a scala compiler plugin (and
accompanying libraries) to improve the performance of generic code. 

Working with primitive types (boolean, int, etc.) generically on the JVM requires that the values be wrapped in an
object, or 'boxed'. Boxing can lead to a lot of allocation and deallocation of small objects (the boxes) as inputs
are unwrapped to get at their values and results of calculations are wrapped up in new boxes. Rapid allocation and
deallocation of objects causes pressure on the garbage collector which can be unacceptable for performance sensitive 
code.

Vlad's solution to this problem is to use a long value (64 bit integer) to wrap primitives, rather than an object. The
technique is known as miniboxing, presumably because a long is a much smaller box than an object.

To make this work, Vlad, with the help of other students at EPFL, needed to implement a compiler plugin and alternate
versions of large parts of the standard library.

Benchmarking has shown that miniboxing can deliver speedups in the range of 1.75x to 2.5x in some cases, though for
some code that has already been aggressively optimized (the [spire](https://github.com/non/spire) numerics library was
given as an example) the impact can be negligible and even negative.

This looks like a really promising idea, but concerns were expressed over whether implementating it as a compiler 
plugin is the best approach. Ideally it would be made available directly in the main scala compiler, but the maintainers
are understandably reluctant to add new features like this until they have been proven to be effective.

**Miniboxing Project Site** - http://scala-miniboxing.org/

Abstract:

> Few people know that miniboxing comes with its own Scala library which has miniboxed arrays, numeric, ordered, tuple and, more interestingly, functions. Without mentioning much, the miniboxing plugin swaps in its optimized library, getting better performance out of your code.
> 
> In this talk I'm going to share some insights on this little secret, explaining why we have a parallel library and how it's implemented. You'll learn about Scala arrays, their invariants, program transformations and many interesting insights into diagnosing performance slowdowns. And you'll see an example of miniboxing in action, improving the performance of a complex Scala class hierarchy.

