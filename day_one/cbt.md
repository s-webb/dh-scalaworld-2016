### CBT: Fast, Intuitive, Convenient Scala Builds - Jan Christopher Vogt

Almost all scala projects are built with sbt. Originally the 'simple' build tool, the name had to be changed
once it had become laughably innacurate. By creating CBT, Jan Christopher Vogt hopes to provide a simpler, faster 
alternative that integrates more naturally with the unix command-line, without losing the flexibility and power that 
are sbts strengths.

This looks like an interesting project, and sbt could certainly do with some competition, but I wonder whether
all of the conceptual bulk of sbt (scopes, axes, configurations, etc.) accumulated for a reason and will either creep
into CBT over time or leak out in other ways.

A couple of great little tools came up during the talk:

- **nailgun:** Startup times for the JVM are ridiculously slow, making it a poor choice for short-lived jobs. Nailgun
(http://www.martiansoftware.com/nailgun/) solves this by keeping a JVM running in the background as a server and using 
a client written in C to run tasks in it.  Bit of a revelation to see Java programs completing (kind of) with single 
digit millisecond duration.

- **coursier**: Coursier (https://github.com/alexarchambault/coursier) can be used as a drop-in replacement for the 
default Ivy dependency resolver used by sbt. Addresses one of the biggest gripes most people have with sbt (aside from 
the fiddly setup); the amount of time spent sat there waiting for the 'Resolving...' message to go away.

**Slides** - https://docs.google.com/presentation/d/1odc1NbkpXPFuhnln-rusB1Dkk3dz7yOeHh0C9WDHodk/

**Earlier version of talk** - http://www.nescala.org/2016/slides/cvogt.pdf

