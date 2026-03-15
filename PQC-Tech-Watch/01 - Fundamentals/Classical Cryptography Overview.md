---
date: 2026-03-02
type: concept
tags:
  - fundamentals
---
## Overview

> [!NOTE]
> <p align="justify">⚠️ This Tech-Watch is not meant to teach deeply about classical cryptography. However, this page is there to provide the minimum amount of information needed to understand the basics. </p>

## What is Classical Cryptography?
**Cryptography** is the science of protecting data using mathematical techniques 
to ensure three critical properties:
- **Confidentiality**: Only authorized parties can read the data
- **Integrity**: Data hasn't been modified in transit or at rest
- **Authentication**: We can verify who created or sent the data

Cryptography uses **algorithms** (mathematical procedures) combined with **keys** (secret parameters) to transform data into a protected, unreadable form that only authorized parties can decrypt. 

While **encryption** is the most common application, cryptography also includes digital signatures, hash functions, and authentication mechanisms.

## Key concepts :
- **Ciphers** are algorithms that transform plaintext into ciphertext using a key
- **Keys** are secret parameters that control the cipher's behavior
- **Decryption** reverses the cipher using the correct key
- **Plaintext** = original, readable data
- **Ciphertext** = encrypted, unreadable data
- Different types of cryptographic primitives serve different purposes: 
  encryption for confidentiality, signatures for authentication, hashes for integrity

## The Three Families 
→ [[Symmetric Key Cryptography]]
→ [[Asymmetric Key Cryptography]]
→ [[Hash Functions]]

## Why This Matters for PQC ?
→ [[Quantum Computing Threat]] 
→ [[What is Post-Quantum Cryptography]]