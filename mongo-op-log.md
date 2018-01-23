# Why there is mongo replication lag ?

- To make mongo resilient , there is a replica that constantly receive the master data and copy
- The replica fetch operations from op log (insert/update/delete) and replay them
- When the replica is slower , a lag is created and if it's too big the whole db as to be resynced and the replica will be unavailable


- Link is weak 
- Replica machine is weaker than primary

