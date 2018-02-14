# Why you should never use maxBy in scala ?

the doc defines the `maxBy` function as follows

```scala
def maxBy[B](f: (A) ⇒ B): A
```

Let's try this in ammonite

```scala
case class A(a:Int)
List(A(1),A(2)).maxBy(_.a)
> res1: A = A(2)

```

Cool very useful , but what about empty list ?

```scala
List.empty[A].maxBy(_.a)
java.lang.UnsupportedOperationException: empty.maxBy

```

Boom ! exception , back to the java stone age 

## Solution use cats maximumOption

```scala

import cats.implicits._
import cats.Order


implicit val orderingByA: Ordering[A]= Ordering.by(_.a)
implicit val orderByA: Order[A]= Order.fromOrdering(orderingByA)

List.empty[A].maximumOption()
res9: Option[A] = None

```

Voila !! no more exceptions , back to scala world
