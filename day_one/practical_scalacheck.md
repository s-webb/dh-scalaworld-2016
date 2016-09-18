### Practical ScalaCheck - Noel Markham

Noel Markham from 47 degrees (a scala consultancy and sponsor of the conference) gave a great introduction to 
property-based testing using the ScalaCheck library.

The approach can be described something like this:

- Specify an invariant for the code under test, e.g. the function to find the absolute value of an int, Math.abs, should
always return a value greater than or equal to zero.

- Describe the range of inputs over which the invariant should hold, e.g. all integer values.

- To run the test, the framework generates a number of inputs (100 by default) and checks that the invariant
holds when the function is applied to each of them.

The generated inputs are not quite random, instead concentrating on boundaries (e.g. Int.MaxValue) where errors are
more likely to occur.

The technique is very effective at finding issues that may have been missed during the original design and/or 
implementation of the code. A good example is the invariant described above for Math.abs, where it will return a 
negative result when passed Int.MinValue as input, because the range of int on the JVM has one more negative value than
positive.

**Slides** - http://noelmarkham.github.io/practical-scalacheck/index.html#/

**Exercises** - http://www.47deg.com/blog/scalacheck-for-scala-exercises

