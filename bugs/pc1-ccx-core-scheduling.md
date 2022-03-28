# PC1 CCX Core Scheduling

## Description

Description of the bug in the issues.

## Related Filecoin Issues

- https://github.com/filecoin-project/rust-fil-proofs/issues/1556
- https://github.com/filecoin-project/lotus/issues/7981

## Desired Implementation

The miner/worker should 

- Run one SDR per core group until all groups are used
- Additional SDR per group if `(1 + FIL_PROOFS_MULTICORE_SDR_PRODUCERS) * [SDR count] <= [core count in group]` (dedicated FIL_PROOFS_MULTICORE_SDR_PRODUCERS)
- loop step 2

Other strategies seem possible:

- Run one SDR per core group until all groups are used
- Additional SDR per group if `([core count in group] - [SDR count] - FIL_PROOFS_MULTICORE_SDR_PRODUCERS) >= 0` (shared FIL_PROOFS_MULTICORE_SDR_PRODUCERS)
- loop step 2

Maybe even a config switch to allow miners to choose what strategy to use.