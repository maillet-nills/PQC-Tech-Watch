---
date: 2026-03-02
type: concept
tags:
  - fundamentals
  - PQC
---
## Overview

> [!NOTE]
> 
> <p align="justify">This page explains what Post-Quantum Cryptography is and why it matters. It's meant as an accessible introduction for readers without cryptographic expertise.</p>

## What is Post-Quantum Cryptography?

**Post-Quantum Cryptography (PQC)** refers to cryptographic algorithms that are thought to be secure against attacks by quantum computers.

Currently, most of our digital security (like RSA or ECC) relies on mathematical problems that a powerful quantum computer could solve in minutes. This is the [[Quantum Computing Threat]] : our most important encryption methods are mathematically vulnerable to quantum attacks.

This makes PQC a critical field of research today because we must upgrade our global encryption standards before quantum computers reach sufficient scale. It's a major challenge for the future of cybersecurity and data privacy.

## The Core Difference: Classical vs Post-Quantum

Classical encryption algorithms (RSA, ECC) are based on mathematical problems that are hard for classical computers but easy for quantum computers using Shor's Algorithm. They're mathematically "broken" by quantum computers.

Post-quantum algorithms are based on different mathematical problems that remain hard for both classical and quantum computers. The goal is to find mathematical foundations that quantum computers cannot exploit efficiently, even in theory.

Think of it as changing the lock entirely rather than just making it bigger. A bigger RSA key won't help if quantum computers can break the fundamental math behind it.

## Key Characteristics of PQC Algorithms

PQC candidates generally fall into these families based on their mathematical foundation:

- **Lattice-based cryptography:** Relies on the hardness of finding short vectors in high-dimensional lattices (ex : [[ML-KEM]], [[ML-DSA]])
- **Hash-based cryptography :** Uses cryptographic hash functions to create signatures
- **Code-based cryptography :** Based on the hardness of decoding random linear codes
- **Isogeny-based cryptography :** Uses mathematical properties of elliptic curve isogenies
- **Multivariate polynomial cryptography :** Based on solving systems of multivariate polynomial equations

Each family has different trade-offs in security assumptions, key sizes, signature sizes, and computational speed.

## Why We Can't Just Use Longer Keys?

**A common misconception is "why don't we just make RSA keys even bigger ?" :**

The answer is that the quantum threat isn't just about key size. [[Shor's Algorithm]] fundamentally breaks the mathematical problem that RSA depends on. Making a key 100 times larger won't help when the algorithm exploits the mathematical structure itself, not just brute force strength.

With symmetric encryption (like AES), we can use [[Grover's Algorithm]] defense by simply doubling key size. But with asymmetric encryption, the math itself is broken, not just the key length.

## The Migration Challenge

**This is why PQC is so urgent and complex :**

**Changing global cryptographic infrastructure takes decades. Organizations can't upgrade overnight. They must :**

- Deploy PQC algorithms gradually across billions of devices
- Ensure compatibility with existing systems during transition
- Test that new algorithms don't introduce new vulnerabilities
- Train developers and security teams on new tools
- Update hardware, firmware, certificates, and protocols

Meanwhile, the "[[Harvest Now, Decrypt Later]]" threat is already happening. Opponents are storing encrypted data today, betting they'll decrypt it with future quantum computers.

## Current Status: NIST Standardization

The U.S. **National Institute of Standards and Technology (NIST)** completed standardization of the first post-quantum algorithms in 2024 :

- **ML-KEM (CRYSTALS-Kyber) :** Post-quantum key encapsulation mechanism
- **ML-DSA (CRYSTALS-Dilithium) :** Post-quantum digital signature algorithm

These are the first standardized algorithms. The goal is to give organizations tested, vetted cryptography they can trust. More algorithms may be added as research continues.

-> [[NIST]]
-> [[ML-KEM]]
-> [[ML-DSA]]

## Hybrid Approaches: Gradual Transition

Many organizations are adopting hybrid approaches during the transition period. They use both classical and post-quantum algorithms together in cryptographic operations. If one is broken, the other protects the data. This buys time during migration and provides defense in depth.

**Example :** An HTTPS connection might use both ECC and ML-KEM for key exchange. Breaking either one isn't enough to compromise the connection.

## Key Concepts

- **Quantum-resistant :** An algorithm that remains secure even against attacks by practical quantum computers
- **NIST standardization :** NIST's formal process to evaluate, test, and approve cryptographic algorithms for government and commercial use
- **Hybrid cryptography :** Using multiple algorithms (classical and post-quantum) together for defense in depth
- **Migration timeline :** The period during which organizations transition from classical to post-quantum algorithms
- **Key size/signature size trade-off :** PQC algorithms often have larger keys or signatures than classical algorithms, which affects storage and bandwidth
- **Lattice problem :** A mathematical problem used by some PQC algorithms; finding short vectors in high-dimensional grids is thought to be quantum-resistant
- **Backward compatibility :** Ensuring new PQC systems can coexist with existing classical cryptography during transition

## Why This Matters for Your Organization

**Post-quantum cryptography isn't just academic research. It's becoming infrastructure reality :**

- Governments are mandating PQC adoption (NIST, European Commission, others)
- Cloud providers are testing PQC integration
- Browsers are beginning PQC trials (Google, others)
- Organizations handling sensitive long-term data must plan migration now

If your data needs to remain confidential beyond 10-15 years, you should be thinking about PQC migration today. The algorithms exist. The work is implementation and deployment.

## Why This Matters for Security & Privacy

**Post-quantum cryptography directly addresses two fundamental questions:**

**Does confidentiality matter after quantum computers exist ?** 
-> If someone stores your encrypted communications today, PQC ensures those messages remain private even after quantum computers arrive.

**Can we transition safely ?** 
-> PQC development gives organizations the tools and time to upgrade cryptographic infrastructure before a quantum threat becomes practical, rather than scrambling after.

## Links
-> [[Quantum Computing Threat]]
-> [[NIST]]
-> [[ML-KEM]]
-> [[ML-DSA]]
-> [[Cryptographic Agility]]
-> [[Harvest Now, Decrypt Later]]