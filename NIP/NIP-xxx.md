# NIP-300: Event Data

**Status:** `Optional` `Draft`

This NIP introduces event data for specific interactions while respecting the limitations of the Nostr protocol and the Lightning Network.

Based on: NIP-01, NIP-02, NIP-04, NIP-09, NIP-28, NIP-46, and NIP-47.

## Event Descriptions

- **Event A:** Alice combines with Bob to open a channel with him (e.g., DMs, chat channels, etc.).
- **Event B:** Bob accepts Alice’s request, and they mutually open a channel.
- **Event C:** DLC verifies both parties using multisig or MuSig.

## Definition of Terms

- `pp`: A tag that indicates a peer.
- `p`: PubKey.
- `event`: A tag indicating an event within a chat on the client.
- `c`: A tag that indicates an open or closed channel.
- `locktime`: A tag that specifies when to close a channel, using a Locktime format.
- `dlc`: A tag indicating DLCs and related events.
- `Kind:30090`: Event type identifier.

## Proof of Concept

We created a proof of concept around this idea.

[More details](https://github.com/AreaLayer/Lightning-lending-PoC/blob/main/poc.rs)

## Specifications

- **Event A:** Two `pp` tags in the `event`.
- **Event B:** Both `pp` tags agree to open or close a channel (`c`).
- **Event C:** With the `dlc` tag, DLC verifies both parties through multisig and MuSig.

## Example Implementation

Below is an example of an event based on the NIP:

```json
{
  "id": "xxx",
  "pubkey": "xxx",
  "created_at": "xxx",
  "kind": "xxx",
  "input": "np12",
  "output": "np13",
  "pp": "np13",
  "c": "np12",
  "locktime": "block 78888",
  "content": "xxx",
  "sign": "xxx",
  "dlc": "open block 6777 and close 78888",
  "hex": "1282893",
  "event": "event124"
}
```

## Signature

Signatures can be implemented using [NIP-46](https://github.com/nostr-protocol/nips/blob/master/46.md), allowing safe signature exchanges between peers using Nostr Connect.

## Compatibility

This NIP is compatible with NIP-01, NIP-02, NIP-04, NIP-09, NIP-28, NIP-46, and NIP-47. Relays/clients will need to add support for the following tags:

- `pp`: A tag indicating a peer.
- `event`: A tag indicating an event within a chat on the client.
- `c`: A tag indicating an open or closed channel.
- `locktime`: A tag specifying when to close a channel, using a Locktime format.
- `dlc`: A tag indicating DLCs and related events.

---

## Implementation

[Lightning Lending:  Open/close channel on Lightning Network using Nostr and DLCs](https://github.com/AreaLayer/Lightning-Lending)
