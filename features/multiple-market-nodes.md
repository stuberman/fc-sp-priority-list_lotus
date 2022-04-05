# Multiple Market nodes serving storage deals and retrieval

## Description
Today its only possible to have one market node attached to the miner. It seems like boost will also only allow one node operation. 
This gets to become a bottleneck, when we want to ingest large amounts of real client data. 
Think of an SP can have a sealing cluster of 100s of servers, but all client data needs to enter through a single market node...  

## Related Discussions/Issues/etc.
Many conversations about this since developing the market node functionality. Latest here: 
https://github.com/filecoin-project/lotus/issues/8408

## Desired Implementation
1. N+1 scale out and elastic attachment of market nodes. 
2. Storage deals, Deal imports and transfers to sealing cluster is load balanced through a scheduler. 
3. Shared storage for retrieval (all online market nodes would be able to serve the client with data)
4. Multiple market nodes will create high availablity of serving clients (internet facing service) 
