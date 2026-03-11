---
title: "Starting This Notebook"
date: 2026-03-10
---

I've been meaning to start writing things down for a while.

Most of my time lately has gone into zero-knowledge systems, especially things around Noir, Go and the intersection between AI ethics and zero knowledge systems. I spend a lot of time experimenting with ideas for fun, reading code, and building small tools to understand how these systems actually work.

This site is basically a place to collect those notes.

Some posts will be short write-ups about things I'm trying to understand. Others will be notes from projects I'm building, experiments that worked (or didn't), or rough explanations of concepts that took me a while to wrap my head around.

Right now I'm working on a couple projects around the Noir ecosystem.

One of them is `noir-go`, which embeds the Noir compiler in WASM so Go programs can compile Noir circuits without needing the full Noir toolchain.

Another recent one is `noir-gnark`, which experiments with translating ACIR into gnark constraints so proofs can be generated entirely from Go.

The rough idea looks like this:

Noir circuit → ACIR → R1CS → Groth16 proof

The goal is to make Go a first-class environment for working with Noir circuits.

I'll probably write about things like:

- constraint systems
- ACIR and R1CS
- proof systems
- Go tooling around ZK
- experiments around verifiable AI systems

Some posts will probably be rough drafts or thinking-out-loud notes. That's intentional. This is meant to be more of a notebook than a polished publication.

If something here is useful to someone else working on similar problems, that's a nice bonus.
