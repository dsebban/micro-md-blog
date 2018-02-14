# What does IO wait time means and how it helps me ?


Definition of IO wait : 

For a given CPU, the I/O wait time is the time during which that CPU was idle (i.e. didn’t execute any tasks) and there was at least one outstanding disk I/O operation requested by a task scheduled on that CPU (at the time it generated that I/O request).

```shell
iostat -x 1
```

Check the `wait` column and the `%util` at the bottom


If wait is 0 it means you are good :)




References : 
- http://veithen.github.io/2013/11/18/iowait-linux.html
- https://serverfault.com/questions/12679/can-anyone-explain-precisely-what-iowait-is