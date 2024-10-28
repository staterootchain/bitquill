# Description

BitQuill is a protocol for providing reasonable evidence of
human-incremental creation of digital documents through proof-of-work
and temporal hash chains. The system creates an unforgeable record of
document evolution by requiring computational work for each edit
operation, making it prohibitively expensive to forge a document’s
writing history after the fact.

# Features

  - Rich text editing with automatic proof-of-work generation

  - Blockchain-anchored timestamps via OpenTimestamps

  - Hash chain verification for document integrity

  - Document serialization and verification

  - Browser-based implementation using Web Crypto API

  - No trusted third parties required

# Technical Overview

BitQuill implements "proof-of-edit" - a novel cryptographic protocol
that creates unforgeable evidence of the human writing process. Each
editing session creates a chain of hashes where each entry H(i) is
computed as:

    H(i) = SHA256(H(i-1) || ContentHash(i) || Timestamp || Nonce)

The system includes difficulty adjustment calibrated to human typing
speeds, making edits computationally inexpensive during normal writing
but prohibitively expensive when attempting to forge an entire document
history.

# Getting Started

1.  Clone the repository

2.  Open index.html in a modern browser

3.  Start writing - the system automatically generates proofs

# Requirements

  - Modern web browser with Web Crypto API support

  - Active internet connection for OpenTimestamps anchoring

# Security Model

BitQuill’s security rests on several key assumptions:

  - Computational difficulty of forging proof-of-work chains

  - Immutability of Bitcoin blockchain timestamps

  - Collision resistance of SHA-256

  - Temporal constraints of human writing speed

# Implementation Notes

The current JavaScript implementation serves as a proof of concept.
While functional, it faces inherent limitations from browser-based
cryptography and JavaScript’s single-threaded nature.

# Future Work

  - Native client implementation

  - Memory-hard proof-of-work function

  - Multi-party witnessing networks

  - Enhanced difficulty adjustment algorithms

  - Distributed storage integration

# Limitations

  - Requires continuous network connectivity for timestamping

  - Browser-based proof-of-work has performance constraints

  - Cannot prevent out-of-band content generation

  - Difficulty adjustment may need tuning for different writing styles

# License

This project is licensed under the GNU General Public License v3.0 - see
the LICENSE file for details.

# Author

Nick @Ciphernom
