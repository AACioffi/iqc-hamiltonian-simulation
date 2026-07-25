# Trotterised Simulation of the Transverse-Field Ising Model

An implementation of first-order Trotter Hamiltonian simulation, applied to
the transverse-field Ising model on a ring of $n$ qubits. Executed on both
Qiskit's ideal simulator and IQM Garnet hardware via qBraid.

**Authors:** Alessandro Annibale Cioffi, Ameli Velasco Duran

**Course:** CS-308, Introduction to Quantum Computation, EPFL (Spring 2026)

## Overview

This project develops an approximate Hamiltonian simulation algorithm and
applies it to a canonical model of quantum magnetism:

- **Theoretical foundations** (Part I): properties of the matrix exponential,
  circuit implementations of Pauli-string exponentials via CNOTs, Hadamards
  and rotation gates, and derivation of the first-order Trotter error bound.
- **Implementation** (Part II): a from-scratch Qiskit implementation of
  Trotterised evolution for

  $$H = -J \sum_{i=0}^{n-1} Z_i Z_{i+1 \bmod n} - h \sum_{i} X_i,$$

  benchmarked against exact evolution. Investigates the empirical all-zeros
  probability $p_0(t)$ and total magnetisation $\langle M \rangle$ across
  regimes of transverse-field strength $h$ and Trotter step count $r$, on
  both Qiskit's ideal simulator and IQM Garnet hardware via qBraid.

## Structure

- `part1/`: Part I handout and theory report
- `part2/`: Part II handout, implementation report, Jupyter notebook, and exact-evolution reference data (`mz_exact_results.json`, `p0_exact_results.json`)

## Requirements

```
pip install qiskit qbraid numpy matplotlib
```

## Note on qBraid Credentials

The real-device sections of the notebook require a qBraid API key to submit
jobs to IQM Garnet. The key originally used during development has been
rotated and purged from the git history. Downstream users must supply their
own key through the appropriate environment variable or qBraid configuration
before running the hardware cells.

## Note on Visibility

Public release of this repository was authorised by Prof. Thomas Vidick.
See `PublicRepo-Authorisation-Proof.png` at the root of the repo.
