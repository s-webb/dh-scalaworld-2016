### Compilers are (in memory) Databases - Martin Odersky

Monday's keynote was given by Martin Odersky, the creator of the scala language.
He started with a brief history of the various compiler architectures he has worked on, before explaining
how the design of current project dotty (a ground-up rewrite of the scala compiler) has been inspired by functional
reactive database systems.

Dotty is still a work-in-progress and not likely to replace the current scala compiler for a couple of years at least,
that said, it is already complete enough to bootstrap itself and able to compile a number of existing OSS libraries.
Throughput (lines of code compiled per second) is reportedly twice that of the existing scalac and Martin expects that
to increase to a factor of three or four times before release.

