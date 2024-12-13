---
layout: page
title: Specification
permalink: /specification/
---

Where applicable, Clatter tracks the latest Noise protocol framework 
specification. For post-quantum features, Clatter conforms to the proposals
defined in the [PQNoise paper](https://doi.org/10.1145/3548606.3560577),
with the following additions and changes:

## Omitting IKEM

PQNoise presents the possibility to configure initiator's (IKEM), responder's (RKEM) and the ephemeral (EKEM) KEM separately. Clatter
does not fully support this, but rather allows to separately configure
the ephemeral (EKEM) and static (SKEM) KEM.

## Protocol Naming

Noise defines the *protocol name* to be used as a basis for the handshake
hash. It is thus important to follow an unambiguous naming scheme for
the sake of cross-implementation compatibility.

For all the classical patterns and crypto primitives Noise specification
defines the naming scheme but there is no definite source for naming
post-quantum primitives as the PQNoise paper does not propose any naming
schemes. Naming for the post-quantum *handshake patterns* by PQNoise is
achieved simply by prepending `pq` to the handshake pattern name.

### PQ Primitive Names

To fill in the gaps, Clatter proposes and uses the following names for
post-quantum primitives:

| Primitive     | Name          |
| ---           | ---           |
| Kyber 512     | `Kyber512`    |
| Kyber 768     | `Kyber768`    |
| Kyber 1024    | `Kyber1024`   |
| ML-KEM-512    | `MLKEM512`    |
| ML-KEM-768    | `MLKEM768`    |
| ML-KEM-1024   | `MLKEM1024`   |

Note that the name of *Kyber* was changed to *ML-KEM* during the selection
process and not all crates have migrated to using the new name. Clatter
uses whatever name the underlying implementation has chosen to use.

### KEM in the Protocol Name

PQNoise simply places the KEM name in place of the DH protocl name in the
classic Noise naming scheme.

However, as Clatter allows to use different KEMs for ephemeral and static
operations, this needs to be reflected in the protocol name as well. If the
KEMs happen to be different, the resulting KEM string in the protocol name
will be constructed by joining the two KEM names together with a `+` symbol,
the ephemeral KEM first.

### Examples

```
Noise_pqIK_MLKEM512_ChaChaPoly_BLAKE2s
Noise_pqNN_Kyber512+Kyber1024_ChaChaPoly_BLAKE2s
Noise_pqXX_Kyber1024+MLKEM512_ChaChaPoly_BLAKE2s
```