# How to prevent reactive-kafka to write in parallel?

Use case: I want to convert a mongo collection to a kafka topic using mongo `find({})` and to keep the same order.

- Reduce kafka producer parallelism to 1 

```scala
producerSettings.withParallelism(1)
```

- define the sort order in mongo using sort query

```scala 
BSONDocument("order.property" -> 1)
```

You can still get reordering when a commit failure occur , but it should be fairly rare.
