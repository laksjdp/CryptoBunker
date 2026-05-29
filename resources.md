# 🎯 Solidity Bug Bounty Hunter's Ultimate Resource Library
- **Point 1:** The best bug hunters don't just find bugs — they understand the *business logic* and find *invariant violations*. Focus less on syntax errors and more on broken assumptions.
- **Point 1:** ...


- ***Fuzzing & Invariant Testing*** - [Foundry](https://getfoundry.sh/), [Echidna](https://github.com/crytic/echidna) & [Medusa](https://github.com/crytic/medusa)
- ***Other Links*** - [Layout in Storage](https://docs.soliditylang.org/en/latest/internals/layout_in_storage.html), [Cheatsheet](https://docs.soliditylang.org/en/latest/cheatsheet.html), [EVM Codes](https://www.evm.codes/), [OWASP Top10](https://github.com/OWASP/www-project-smart-contract-top-10), [Audit Readiness Checklist](https://www.quillaudits.com/blog/web3-security/smart-contract-audit-readiness-checklist), [SC Exploits Minimized](https://github.com/Cyfrin/sc-exploits-minimized), [Secure Contracts](https://secure-contracts.com/), [Verified Smart Contracts](https://github.com/runtimeverification/verified-smart-contracts)


## 📚 Learning Platforms & Courses
| Resource | Purpose |
|----------|---------|
| [Smart Contract Security Field Guide](https://scsfg.io/) | Free security reference |
| [Secure Contracts](https://secure-contracts.com/) | In-depth security patterns |
| [Ethereum Documentation](https://ethereum.org/en/developers/docs/) | Official EVM docs |

---
## 💰 Bug Bounty Platforms
| Platform | Focus |
|----------|-------|
| [Immunefi](https://immunefi.com/) | Highest payouts, major protocols |
| [CodeHawks](https://www.codehawks.com/) | Competitive audits |
| [Hats Finance](https://hats.finance/) | Bug bounties + audits |
| [Code4rena](https://code4rena.com/) | Competitive audit contests |
| [Sherlock](https://www.sherlock.xyz/) | Auditing competitions |
| [Cantina](https://cantina.xyz/) | Competitive audits |

---
## 🛠️ Essential Tooling

### Static Analysis
| Tool | Link | Best For |
|------|------|----------|
| [Slither](https://github.com/crytic/slither) | Comprehensive static analysis |
| [Aderyn](https://github.com/Cyfrin/aderyn) | Rust-based fast analyzer |
| [Mythril](https://github.com/Consensys/mythril) | Symbolic execution |
| [4nalyzer](https://github.com/Picodes/4nalyzer) | Quick automated scans |

- ***Formal Verification*** - [Certora](https://www.certora.com/), [Halmos](https://github.com/a16z/halmos), [Kontrol](https://github.com/runtimeverification/kontrol)

### Auxiliary Tools
| Tool | Link | Purpose |
|------|------|---------|
| cloc | https://github.com/AlDanial/cloc | Code line counting |
| EVM Diff | https://www.evmdiff.com/ | Contract comparison |
| UpgradeHub | https://upgradehub.xyz/ | Proxy analysis |
| Tenderly | https://tenderly.co/ | Debugging & simulation |
| Wise Signer | https://wise-signer.cyfrin.io/ | Signature verification |

---

## 🔬 Vulnerability Knowledge Base
- ***Exploit Databases*** - [Solodit](https://solodit.xyz/), [Rekt News](https://rekt.news/), [Web3 Bugs Dataset](https://github.com/ZhangZhuoSJTU/Web3Bugs), [SC Exploits Minimized](https://github.com/Cyfrin/sc-exploits-minimized), [DeFi Hacks Reproductions](https://github.com/SunWeb3Sec/DeFiHackLabs)

- ***Attack Pattern Libraries*** - [Weird ERC20 List](https://github.com/d-xo/weird-erc20), [Reentrancy Attacks](https://github.com/pcaversaccio/reentrancy-attacks), [Solidity Hacks by Example](https://solidity-by-example.org/hacks/), [Weak Randomness Examples](https://github.com/Cyfrin/sc-exploits-minimized/tree/main/src/weak-randomness)

- ***📝 Report Writing & Templates*** - [Severity Guide](https://docs.codehawks.com/hawks-auditors/how-to-evaluate-a-finding-severity), [Cyfrin Report Template](https://github.com/Cyfrin/audit-report-templating), [Spearbit Template](https://github.com/spearbit-audits/report-generator-template)


- ***📰 Newsletters & Threat Intel*** - [Block Threat Intel](https://newsletter.blockthreat.io), [Consensys Diligence](https://consensys.io/diligence/newsletter/), [REKT Newsletter](https://rekt.news/newsletter/), [Flashbots MEV](https://flashbots.substack.com/)

---
## 📖 Blogs & Research (Must Follow)

- ***Security Firms*** - [Trail of Bits](https://blog.trailofbits.com/), [OpenZeppelin](https://blog.openzeppelin.com/), [Sigma Prime](https://blog.sigmaprime.io/), [PeckShield](https://peckshield.com/en/blog), [SlowMist](https://slowmist.medium.com/), [Halborn](https://www.halborn.com/blog/)

- ***Individual Researchers*** - [samczsun](https://samczsun.com/), [Tincho](https://twitter.com/tinchoabbate), [Pashov](https://pashov.net/blog/), [0xKage](https://twitter.com/0xkage), [DevDacian](https://github.com/devdacian)

- ***Aggregators*** - [Week in Ethereum News](https://weekinethereumnews.com/), [Ethereum Stack Exchange](https://ethereum.stackexchange.com/)


- ***📋 Checklists & Methodologies*** - [Simple Security Toolkit](https://github.com/nascentxyz/simple-security-toolkit), [Solcurity (Transmissions11)](https://github.com/transmissions11/solcurity), [Auditing Heuristics](https://github.com/OpenCoreCH/smart-contract-auditing-heuristics), [Cyfrin Audit Checklist](https://github.com/Cyfrin/audit-checklist), [OpSec Roadmap](https://github.com/OffcierCia/Crypto-OpSec-SelfGuard-RoadMap), [Audit Readiness Checklist](https://www.quillaudits.com/blog/web3-security/smart-contract-audit-readiness-checklist), [OWASP Smart Contract Top 10](https://github.com/OWASP/www-project-smart-contract-top-10)

---

## 🔥 The Rekt Test (12 Questions)
> *From Trail of Bits - can you pass this?*

1. Do you have all actors, roles, and privileges documented?
2. Do you keep documentation of all external services, contracts, and oracles you rely on?
3. Do you have a written and tested incident response plan?
4. Do you document the best ways to attack your system?
5. Do you perform identity verification on all employees?
6. Do you have a team member with security defined in their role?
7. Do you require hardware security keys for production systems?
8. Does your key management require multiple humans and physical steps?
9. Do you define key invariants and test them on every commit?
10. Do you use the best automated tools to discover security issues?
11. Do you undergo external audits and maintain a bug bounty program?
12. Have you considered and mitigated avenues for abusing users of your system?

---

## 🧠 Core Principles to Memorize

```
Checks → Effects → Interactions (CEI)
FREI-PI (For Reentrancy)
Pre-checks → Post-checks
Pull over Push for payments
```

---

## 🗺️ Bug Hunter's Roadmap

```
┌─────────────────────────────────────────────────────────────────┐
│                         ROADMAP TO BOUNTY                        │
├─────────────────────────────────────────────────────────────────┤
│                                                                  │
│  📖 LEARN          🛠️ TOOL          🎮 PRACTICE       💰 HUNT    │
│  ─────────────────────────────────────────────────────────────  │
│  • EVM/Gas        • Slither        • Ethernaut      • Immunefi  │
│  • Solidity       • Foundry        • Damn Vulnerable • CodeHawks│
│  • ERC standards  • Echidna          DeFi           • Sherlock  │
│  • Attack vectors • Aderyn         • Paradigm CTF   • Cantina   │
│                                                                  │
│  📚 STUDY REAL BUGS → Solodit / Rekt News                       │
│  ✍️ WRITE POCs → Prove your vulnerability                       │
│  🎯 COMPETE → Competitive audits first!                         │
│                                                                  │
└─────────────────────────────────────────────────────────────────┘
```

---

## 🚀 Pro Tips

> *"Don't read docs cover-to-cover. Focus on EVM, Gas, Token Standards, and Advanced sections (Bridges, Oracles, Scaling)."*

**Highest bounty areas:**
- Cross-chain bridges (critical)
- Price oracle manipulation (flash loan attacks)
- Governance attacks
- Access control in upgradeable proxies

**Must know before hunting:**
1. Write a Proof of Concept (PoC) using Foundry
2. Fork mainnet to test realistic scenarios
3. Read 50+ real audit reports on Solodit
4. Complete Ethernaut + Damn Vulnerable DeFi

---

## 🔗 Quick Reference Card

| Need | Go Here |
|------|---------|
| Real bug examples | Solodit |
| Practice targets | Audit repos above |
| CTF practice | Ethernaut |
| Tool setup | Foundry book |
| Report template | Cyfrin template |
| Live bounties | Immunefi |
| Community | Cyfrin/CodeHawks Discord |
