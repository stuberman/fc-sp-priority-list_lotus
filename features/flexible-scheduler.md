# Flexible scheduler

## Description

The current lotus scheduler implementation has certain downsides that does not allow a storage providers to get the max. out of the hardware they are running. Having a general implementation that works on top of resource availability is great and should be kept. A flexible scheduler should aim to amend the current implementation and allow for storage providers to replace it with their own scheduler logic.

## Related Discussions/Issues/etc.

An example of this being planned/implemented: https://github.com/filecoin-project/devgrants/issues/445

Input from Jonathan: The scheduler needs to be manipulated for different tech designs. For example, when it fails over it can't correct its self. It's easier to turn off and start again. We just want a very simple round robin on PC1s.

Issues:

https://github.com/filecoin-project/lotus/issues/7868

https://github.com/filecoin-project/lotus/issues/7607


## Desired Implementation

To be filled in by @f8-ptrk
