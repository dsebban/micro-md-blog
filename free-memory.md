# How much memory do I have left on my server ?

```bash
$ free -m
             total       used       free     shared    buffers     cached
Mem:        122884     122198        686          0        301      47944
-/+ buffers/cache:      73951      48932
Swap:            0          0          0

``` 

The `free` of the first column is misleading, the real free memory is the one
on the `-/+` line .

Other ways to find out free memory :

- `cat /proc/meminfo`
- `vmstat`
- `htop`