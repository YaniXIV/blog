---
title: "Heterogeneous TEE Attestation: Verifiable Compute"
date: 2026-03-29
---

I recently reached out to a team called Livy Labs who are currently working on content authenticity and provenance, which overlaps a lot with something I'd previously been building called Ventus, a decentralized content authenticity protocol that uses TEE-backed signing and ZK proofs to prove the provenance of media. Instead of asking "is this fake?", you ask "can we prove what's real?"

Through that conversation, I got pointed to an architecture where you run code inside a TEE, it produces an attestation binding the code, input, and output. Kind of like a zkVM but programs run at near-native speed because you're leaning on hardware trust rather than pure cryptographic guarantees.

The obvious critique, one I kept running into with Ventus too, is that you're ultimately just trusting one hardware vendor. Intel, AMD, Apple, whoever. That's still a centralized trust assumption.

But what if you didn't use just one?

Run the same computation on Intel TDX and AMD SEV-SNP. Require that both independently attest to the same result. Now instead of "trust Intel," your assumption becomes "trust that Intel and AMD aren't both compromised in the same way at the same time." Different hardware, different microcode, different firmware, different attack surfaces. That feels like a meaningfully harder thing to break.

I don't know exactly how you'd implement this. You'd parallelize execution across both, then somehow prove they converged on the same output, then possibly compress that into a single ZKP. I'm not sure how much that would interact with the speed goals either, that's a real open question for me. But the end result of one proof you can verify anywhere instead of separately checking two vendor attestation backends seems worth it.

Huge shoutout to **Saúl García Céspedes** — our conversation sparked a lot of this thinking.

Also credit to the **Livy Labs** team — their work clearly points in a direction that feels both practical and powerful.

References:
- [Livy: The Universal Provenance Layer](https://www.livylabs.xyz/blog/universal-provenance-layer)
- (https://colab.ws/articles/10.1145%2F3719653)
- (https://dl.acm.org/doi/pdf/10.1145/3594556.3594626)
- (https://dl.acm.org/doi/10.1145/3622781.3674168)

*(Some references not fully explored yet — included for future deep dives.)*
