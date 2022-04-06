# Lotus-workers shared between multiple lotus-miners
## Description
Most big SPs have multiple miners running, but is manually allocating sealing workers between these as needed. 
It would be a great benefit if Sealing Workers and PoST Workers could just be one shared pool between all these miners. 

## Related Discussions/Issues/etc.
https://filecoinproject.slack.com/archives/CEGN061C5/p1649146857166379

## Desired Implementation
1. Separate out the scheduler proces from the lotus-miner
2. Make the scheduler handle N number of PoST and Sealing workers, and connect to N number of lotus-miners. 
