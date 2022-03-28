# notifs channel closed

## Description

Sometimes the lotus processes close the notifs channels and communication between processes fails. This leads to unpleasant to painful errors like failed wdPosts. 

notifs channels seem not to be re established reliably after they closed.

## Related Filecoin Issues

- https://github.com/filecoin-project/lotus/issues/8362
- https://github.com/filecoin-project/lotus/issues/7653
- https://github.com/filecoin-project/lotus/issues/6883
- https://github.com/filecoin-project/lotus/issues/5813

## Desired Implementation

At least:

- an entry for notifs channels in `lotus-miner log alerts` indicating that channels are OK/not OK

Better:

- an API endpoint to query the status of notifs channels

Ultimately:

- notifs channels being reliably reopened when closed or notifs channels not closing at all