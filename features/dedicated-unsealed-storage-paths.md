# [Dedicated unsealed storage paths]

## Description

The ability to store the unsealed sector copy in dedicated storage paths. This feature will help with scaling a mining operation. Currently the unsealed sectors can only be stored in the secor store storage - that make access slow and, for the sealed sectors, redundancy schemes overly complicated. 

This storage should be able to live as close to the markets node (or if implemented boost) process for faster retrieval.

by Julien @twin quasar

## Related Discussions/Issues/etc.

slack internal discussions / SPWG calls / MinerX calls

## Desired Implementation

A separate storage path class for unsealed sectors. Attachable to the markets node / boost directly if needed.