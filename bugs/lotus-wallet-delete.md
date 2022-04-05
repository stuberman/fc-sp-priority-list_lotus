# Lotus wallet delete - actually delete/remove the key

## Description

Currently, when executing `lotus wallet delete` the key does not get deleted but moved around on the node to hide it when executing `lotus wallet list`. Tha t is in the end not the meaning of delete. Operators of a node expect the key to be actually deleted or at least removed for easy access (as proper deletion most likely is out of reach for lotus). 

This is costing unaware miners a lot of money, see this example of a miner that lost control of miner nodes due to the key not actually being deleted:

[https://filecoinproject.slack.com/archives/CPFTWMY7N/p1648824669981009](https://filecoinproject.slack.com/archives/CPFTWMY7N/p1648824669981009)

There will be more cases to find in slack.

## Related Filecoin Issues

https://github.com/filecoin-project/lotus/issues/6926

## Desired Implementation

Lotus actually deleting/removing the key. If that is considered impossible to accurately implement: change the commands name to represent what the command is actually doing: moving the key file to another folder!

