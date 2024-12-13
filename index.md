---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: page
---

[![Crates.io Version](https://img.shields.io/crates/v/clatter?style=flat-square)](https://crates.io/crates/clatter)
[![docs.rs](https://img.shields.io/docsrs/clatter?style=flat-square)](https://docs.rs/clatter/latest/clatter/)

# Quantum-Safe Cryptography for Every Device

Clatter is a `no_std` compatible, pure Rust implementation of the [**Noise protocol framework**](https://noiseprotocol.org/noise.html)
with support for [**Post Quantum (PQ) extensions**](https://doi.org/10.1145/3548606.3560577) (referred to as *PQNoise*) as presented by
Yawning Angel, Benjamin Dowling, Andreas Hülsing, Peter Schwabe, and Fiona Johanna Weber.

Clatter aims to be a modern solution for quantum-safe cryptography, with
absolute emphasis on correctness, extensibility and strict
`no_std` compliance to provide top-notch security even for the smallest
embedded devices. 

Similarly to the classic Noise protocol framework, Clatter is not
a secure communication protocol implementation but rather a customizable
framework for designing protocols for your exact needs. Noise is known to
be *hard to f-up* and with the excellent post-quantum transformations
provided by the PQNoise paper, Clatter brings the same certainty into
quantum-safe protocol design.

# Support

* To report issues or request features, please open a ticket in the
[project repository issues section](https://github.com/jmlepisto/clatter/issues).
* If you are a commercial entity and wish to request larger feature sets,
integration support or other types of consultation, you can reach me via
mail at joni.lepisto@proton.me.