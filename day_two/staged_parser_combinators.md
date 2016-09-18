### Specialising Parsers for Queries - Manohar Jonnalagedda

Parser combinator libraries seem to have a special place in the interests of the scala community. The syntactic
flexibility of the language is ideally suited to the purpose, allowing parsers to be expressed as executable grammars. 
This approach, while very elegant, has downsides. The biggest being that some of the structure of the grammar
(which is fixed when it is written) ends up being evaluated at runtime, giving sub-optimal performance.

Manohar Jonnalagedda (a PhD student at EPFL) has written a parser combinator library that can be used to define
a parser using basically the same grammar as that of parser combinator module in the scala standard library, where
the structure of the grammar is fully evaluated at compile time, thereby reducing the amount of work to be done at 
runtime and significantly improving performance. This approach is known as 'staging'.

Looks like an interesting project, not sure how widely applicable it will turn out to be though.

**Repo** - https://github.com/manojo/parsequery

Abstract:

> In this talk I present parsequery. It uses staging to remove composition overhead at compile time to produce efficient, fast parsers. Its interface is almost similar to Scala's parser combinators.
> 
> The main goal of parsequery is to systematically eliminate all intermediate data structures that are creating when running a traditional parser combinator program. Typically, parser combinators interleave static composition of parsers with the dynamic act of parsing itself, at runtime. The key insight is that we can fully decouple the static parts from the dynamic one.
> 
> The presentation will go over the theory behind it, and how to leverage Scala macros and quasiquotes to implement this optimisation as a library.

