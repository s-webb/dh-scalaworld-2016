### The Type Astronauts Guide to Shapeless - Dave Gurnell

Introductory workshop on shapeless, the generic programming library for scala created by Miles Sabin.

The core construct provided by the library is the HList (for heterogenous list), a data structure where the type (and
number of) elements the list contains is reflected in it's type signature. So, for a list containing a String, an Int
and a Boolean, we'd have something like:

```scala
val strIntBool: String :: Int :: Boolean :: HNil = ???
```

As opposed to the following, which is what you would have if you put the same elements in a standard scala Seq, where
the only information it contains is the closest common ancestor of the element's types (Any):

```scala
val strIntBool: Seq[Any] = ???
```

Shapeless also provides facilities to convert any case class or tuple to and from this representation, and to perform
collection style operations on HLists (e.g. map) in a typesafe manner.

The library can be used to implement functionality that we might otherwise have used reflection for, e.g. take all the
fields of any arbitrary object and write them out as a line of CSV data. The big advantage shapeless has is that this
can all be done without stepping outside the type system, therefore giving the compiler the opportunity to check our
work.

Another thing introduced in this workshop was the concept of a **coproduct** - i.e. the dual of a product, analagous to
a sealed trait in much the same wasy as a HList is analagous to a tuple, in that it provides the same ability to
abstract over type but with greater flexibility (and correspondingly longer type signatures). A simple example would look
like:

```scala
sealed trait Shape
case class Rectangle() extends Shape
case class Circle() extends Shape

type ShapeRepr = Rectangle :+: Circle :+: CNil // CNil is the empty coproduct

```

There's a huge amount more to the library, all built around the same basic idea of typesafe generic programming. It
has made a big impact on the scala ecosystem since the 1.0 release a couple of days before the start of 2012, with at
least 60-odd other libraries depending on it and 80 contributors to the project

One unfortunate aspect of working with shapeless is the insanity of the type signatures. In the picture below, the
first 17 lines on screen constitute the type signature of the function being declared, the body of which is 9 lines
long.  This does not seem to be unusual.
![shapless type signature](../gitbook/images/day_one/shapeless_type_signature.jpg)

**Slides** - https://github.com/davegurnell/shapeless-guide-slides

**Repo** - https://github.com/davegurnell/shapeless-guide

**Book (WIP)** - https://github.com/davegurnell/shapeless-guide/blob/develop/dist/shapeless-guide.pdf
