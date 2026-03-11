---
title: "Projects"
---

A short list of active work.

## noir-go
A Go library for compiling Noir circuits without requiring a local Noir toolchain.

The Noir compiler runs inside an embedded WASM binary using wazero, so Go projects can compile Noir circuits without installing Nargo or Rust. The library resolves the Noir project structure, invokes the compiler, and returns the resulting ACIR artifact along with ABI and witness metadata.

The goal is to make Go a practical environment for working with Noir circuits.

Pipeline stage:

Noir source → **ACIR**

Repository: https://github.com/YaniXIV/noir-go

---

## noir-gnark
A pure Go backend for proving and verifying Noir circuits using gnark.

This project takes the ACIR artifact produced by `noir-go`, translates it into gnark constraints, and generates Groth16 proofs. The goal is to support the full Noir workflow from Go without FFI, Rust dependencies, or external tooling.

Pipeline stage:

ACIR → **R1CS → Groth16 proof**

Repository: https://github.com/YaniXIV/noir-gnark

---

Together these projects aim to support a full Go-native workflow for Noir circuits:

Noir circuit → **ACIR (`noir-go`) → R1CS → proof (`noir-gnark`)**
