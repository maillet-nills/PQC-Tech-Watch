---
date: 2026-03-02
type: concept
tags:
  - fundamentals
  - PQC
  - Shor
  - Grover
  - quantum-threat
---
## Overview

> [!NOTE]
> 
> <p align="justify">This note explains why quantum computers pose a threat to current cryptographic systems. It's designed as an introduction for external readers without deep quantum computing knowledge.</p>

## What is the Quantum Computing Threat?

**Quantum computers** are a fundamentally different type of computer that exploit the strange properties of quantum mechanics, specifically superposition and entanglement, to process information in ways that classical computers cannot.

While classical computers process data as bits (0 or 1), quantum computers use qubits (quantum bits) that can exist as 0, 1, or both simultaneously until measured. This allows quantum computers to explore many possible solutions in parallel, making them exceptionally powerful at solving specific types of mathematical problems.

**The cryptographic threat is real :** most of today's encryption systems (RSA, ECC, Diffie-Hellman) rely on mathematical problems that are hard for classical computers to solve. However, quantum computers can solve these problems efficiently using specialized algorithms like Shor's Algorithm, potentially breaking the security of billions of encrypted communications overnight.

> This isn't theoretical speculation. It's a recognized threat with a timeline. The question is not "if" quantum computers will reach sufficient power, but "when," and whether we'll have migrated to quantum-resistant cryptography by then.

## Key Threats to Current Cryptography

### Shor's Algorithm (Asymmetric Encryption Threat)

- **What it does:** A quantum algorithm that efficiently factors large numbers and computes discrete logarithms
- **What it breaks:** RSA encryption, Elliptic Curve Cryptography (ECC), Diffie-Hellman key exchange
- **Impact:** All public-key encryption and digital signatures currently used for HTTPS, blockchain, and government communications
- **Timeline:** Requires approximately 2 million physical qubits to break current encryption in minutes (far beyond today's quantum computers)

-> Check [[Shor's Algorithm]] for more.

### Grover's Algorithm (Symmetric Encryption Threat)

- **What it does:** A quantum algorithm that searches unsorted databases faster than classically possible
- **What it threatens:** Symmetric encryption like AES, symmetric key lengths
- **Impact:** Reduces security by approximately half (e.g., AES-256 becomes as secure as AES-128)
- **Mitigation:** Already simple — double the key size of symmetric algorithms
- **Status:** Less catastrophic than Shor's, but still requires action

-> Check [[Grover's Algorithm]] for more.

### The "Harvest Now, Decrypt Later" Attack

- **Scenario:** Opponents collect and store encrypted data today, betting they'll have quantum computers in the future to decrypt it
- **Who's affected:** Anyone whose encrypted data has long-term sensitivity (government secrets, military communications, personal health records, financial data)
- **Urgency:** **This threat is already happening now**, even though large-scale quantum computers don't exist yet

-> Check [[Harvest Now, Decrypt Later]] for more.

## Why Current Encryption is Vulnerable

**Classical vs. Quantum advantage:**

|Problem|Classical Computer|Quantum Computer (Shor's Algorithm)|
|---|---|---|
|Factor a 2048-bit number|Thousands of years|Minutes|
|Compute discrete logarithm|Thousands of years|Minutes|
|Search AES key space|Billions of years|Millions of years (Grover)|

The mathematical foundation of RSA and ECC is no longer safe once quantum computers reach sufficient scale. It's not a flaw in the algorithm design. It's a fundamental property of the mathematics involved.

## Key Concepts for Understanding the Threat

- **Qubit** = Quantum bit; can be 0, 1, or both (superposition) simultaneously
- **Superposition** = A quantum property allowing qubits to explore multiple states at once
- **Entanglement** = A quantum property where qubits become correlated; measuring one instantly affects the others
- **Quantum advantage** = A quantum computer solving a problem faster than any known classical algorithm
- **"Q-Day"** = The hypothetical moment when quantum computers become powerful enough to break current encryption
- **Logical qubits** = Error-corrected qubits; require many physical qubits (roughly 1000:1 ratio)
- **Coherence time** = How long a quantum computer can maintain quantum states; longer times allow longer computations

## The Timeline Question

**Honest uncertainty:**

- No one knows exactly when quantum computers will reach the 2+ million physical qubits needed to threaten current encryption
- Estimates range from 10–20+ years, but this could shift with technological breakthroughs
- Some threats (like Harvest Now, Decrypt Later) are active **right now**

**Why we can't wait:**

- Cryptographic infrastructure takes decades to upgrade globally
- Organizations must transition before Q-Day, not after
- "It might be 20 years away" is not an excuse for inaction — the migration requires 10+ years anyway

## Links

→ [[What is Post-Quantum Cryptography]] 
→ [[NIST]] 
→ [[ML-KEM]] 
→ [[ML-DSA]] 
→ [[Shor's Algorithm]] 
→ [[Grover's Algorithm]] 
→ [[Harvest Now, Decrypt Later]]