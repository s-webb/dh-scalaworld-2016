### Make Your Programs Free - Pawel Szulc

Great last-minute live coding session on free monads, covering implementation of a simple algrebra, vertical and
horizontal composition. Worth going through the history of the repo commit-by-commit to see how the final version is
built up, as Pawel did in the talk. Also to observe the content being put together at 2am on the day of the talk!

The intial example is taken directly from the book 'Functional Programming in Scala', published towards the end of
2014. A book I still haven't managed to finish after four attempts.

Szulc presented an interesting way to think about the free monad which actually started to make sense to me (although
I'm not quite sure if it was a moment of revelation or stockholm syndrome). Essentially if you have a `Free[S, A]`,
then you can think of the `Free` as the program you are writing, the `S` as the language (or algebra) you are
writing it in, and the `A` as the value to be produced from your program. It's then possible to make a new program
using a coproduct (basically a union) of two algebras, to compose `Free`s.

To apply this pattern, you also need an interpreter of type `F ~> G` (a "natural transformation", roughly
equivalent to `F[A] => G[A]`). Interpreters can be used to convert between high-level and low-level ops, and can
be composed together with `andThen`.

This talk made heavy use of scalaz, which by the end of it was starting to look like it might be pretty interesting
to use. The main problem with it from my point of view is the excessive use of symbols - something like `~>` is pretty
difficult to pronounce, let alone to google. Cats makes this a bit easier for newcomers by giving its classes names
which are actually words, a pretty radical notion in the FP world.

**Slides** - http://www.slideshare.net/paulszulc/make-your-programs-free

**Code** - https://github.com/rabbitonweb/make-your-programs-free/
