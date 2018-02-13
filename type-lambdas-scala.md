# What's a type lambdas , why do I need it ?

`type` means it's somethings at the type level




##Use a type alias to adapting from kind-2 to kind-1

```scala

trait Functor[F[_]]

type F1 = Functor[Option] // works
type F2 = Functor[Map] // does not work 

```

Map is kind-2 , Functor need a kind-1

Solution : 

```scala

type IntKeyMap[V] = Map[Int, V]  // <- partial application 

type F3 = Functor[IntKeyMap] // works


```


## Can I do it without having a type alias ?

Yes use kind projector plugin 

```scala

 type FG[X] = Functor[({type T[A] = })#T]

def compose[G[_]](implicit G: Functor[G]): Functor[Lambda[X =>F[G[X]]]]  = ???
 

```

