# NIP-xxx: Peers Lightning

`author:22388oo` `optional` `draft`

The NIP follows special events and respecting limits of Nostr protocol and Lightning Network

Based on NIP-01, NIP-02, NIP-04, NIP-09, NIP-28, NIP-46 and NIP-47

- Event A: Alice commbines with Bob open channel with him
- Event B: Bob accepts Alice and get together open a channel
- Event C: DLC verify both parties, multisigs, musig

## Definition

- `p`: Tag must be present that indicate peer
- `event`: Tag indicates event inside chat on client
- `c`: Tag indicates open or close channel 
- `dlc`: Tag indicates DLCs and event

## PoC

We created a proof of conecpt around this idea 

[More details](https://github.com/AreaLayer/Lightning-lending-PoC/blob/main/poc.rs)


## Specs

- `Event A`: Two `p` into `event`

- `Event B`: The two `p` accepts open `c` or closec channel

- `Event C`: With `dlc`tag the DLCs verify both parties be multisig and musig

##  Example

Follow below the example of the NIP

```json
{
"input":"xxx"
"output":"xxx"
"p":"xxx"
"dlc":"xxx"
"hex:"xxx"
"event":"xxx"
},
