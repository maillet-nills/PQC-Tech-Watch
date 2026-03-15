---
date: 2026-03-15
source: https://echotechno.fr/2026/03/14/chiffrement-https-google-se-prepare-aux-ordinateurs-quantiques/
type: news
tags:
  - active-watch
  - ML-DSA
  - PQC-adoption
  - crypto-agility
  - Google
  - NIST
  - Cloudflare
  - MTC
  - Shor
status: done
cite-key: google_mlksa_https_2026
---
## Summary

Google launches an ambitious program to quantum-harden HTTPS certificates using **Merkle Tree Certificates (MTC)** combined with post-quantum signatures (**ML-DSA**), deployed through **Chrome** browser in collaboration with Cloudflare. Problem solved: MTCs compress post-quantum certificates from 160 KB to 700 bytes. Three-phase deployment plan through Q3 2027, introducing Chrome Quantum-resistant Root Store.

## Key Points

### The Quantum Threat to HTTPS

- Classical HTTPS certificates vulnerable to **Shor's Algorithm** (breaks ECC signature verification)
- Attackers could forge fake X.509 certificates, accepted by browsers without warning
- Historical precedent: **DigiNotar 2011** - 500 forged certificates used to spy on millions worldwide
- Threat is real but timeline unclear: quantum computers powerful enough (millions+ qubits with sufficient coherence) still years away

### Google's Post-Quantum Solution: Merkle Tree Certificates (MTC)

- **ML-DSA** alone creates massive problem: post-quantum certificates ~40x larger than classical (160 KB vs 4 KB for standard X.509)
- Solution: **Merkle Tree Certificates (MTC)** - cryptographic data structure from 1970s mathematics
- MTCs compress millions of certificates into single compact proof/fingerprint
- **Remarkable size reduction**: 700 bytes (MTC) vs 160 KB (classical X.509) = **99.6% reduction**
- Maintains security AND transparency (enhanced with Certificate Transparency logs)

### Deployment Strategy

- **Collaboration**: Google + Cloudflare joint effort
- Currently testing **1,000 certificates** on Chrome with MTC approach
- New certificate architecture: **Chrome Quantum-resistant Root Store** (parallel to existing Chrome Root Program)

### Three-Phase Rollout Plan (through Q3 2027)

1. **Phase 1** (2026-2027): Feasibility study - test performance & security of MTC connections in production
2. **Phase 2** (mid-2027): Deploy first public MTCs with Certificate Transparency log operators
3. **Phase 3** (Q3 2027): Finalize requirements for Chrome Quantum-resistant Root Store + parallel trust anchors

### Implementation Details

- **Algorithm**: ML-DSA (NIST standardization of CRYSTALS-Dilithium) for digital signatures
- No degraded user experience (seamless browser security upgrade)
- Enhanced transparency via Certificate Transparency integration
- Affects all HTTPS connections globally via Chrome dominance (~65% market share)

## Links to other concepts

→ [[NIST]]
→ [[ML-DSA]] 
→ [[What is Post-Quantum Cryptography]] 
→ [[Cryptographic Agility]] 

## Open Questions

- What is the exact performance impact: MTC verification time vs classical certificate validation on Chrome ?
- How will MTC deployment affect TLS 1.3 handshake performance and latency ?
- When will MDCs be mandatory vs optional for new certificates ?
- Will Android Chrome, iOS Chrome, and Chromium-based browsers (Edge, Brave, Opera) support MTCs on same timeline ?
- How does Chrome Quantum-resistant Root Store interact with existing Root Program trust anchors ?
- What testing has Google completed to ensure zero HTTPS breakage during MTC roll out ?
- Will legacy sites/old servers need immediate updates, or is there backward compatibility layer ?
- Timeline for Firefox, Safari, Edge to adopt MTC approach - will they follow Google or pursue alternatives ?
- How will Certificate Transparency logs be updated to accommodate MTC signatures ?
- What is the cost/performance impact for Certificate Authorities implementing MTC support?