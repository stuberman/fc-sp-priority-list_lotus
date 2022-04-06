# Finalize the work on splitstore (auto-prune the chain data)
## Description
Seems like splitstore really never got out of testing. It would be nice to get this done, but not only stop by having hot/cold storage,
but more important having a feature that automatically prunes the cold store. 

## Related Discussions/Issues/etc.
https://github.com/filecoin-project/lotus/discussions/5788

## Desired Implementation
Have a variable that controls how many recent-stateroots is held in hot and cold

- Hot behavior: All stateroots > thresshold is moved to cold storage
- Cold behavior: All stateroots > thresshold is deleted/pruned

Outcome: Ongoing static usage of disk space on daemon device
