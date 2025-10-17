# Poster — Analysis of Leakage Suppression in Transmon Qubits Under Different DRAG Drives

This repository contains the poster presented at the International Workshop on Quantum Technology (IWQT) 2025, focused on the analysis of leakage suppression techniques in multilevel superconducting transmon qubits.

# Overview

Superconducting transmon qubits — the workhorses of modern quantum processors — suffer from low anharmonicity and frequency crowding (|α/2π| in the range of 150–300 MHz), which often leads to spectral overlap of control pulses with higher transitions such as |1⟩ ↔ |2⟩.
This overlap causes leakage errors, which are a major limitation in achieving high-fidelity quantum gates.

This work presents a comparative simulation and analysis of several DRAG-based pulse-shaping techniques that suppress leakage while maintaining fast and high-fidelity single-qubit gates.

# Methods

The following drive schemes were simulated and compared within a three-level transmon model for an X-gate implementation:
Standard DRAG
Fifth-Order DRAG (with time-dependent detuning)
FAST DRAG — Fourier Ansatz Spectrum Tuning
HD DRAG — Higher Derivative DRAG

The rotating-frame Hamiltonian used for analysis is given by:

HR = Σj [ δj |j⟩⟨j| + (I(t)/2)σx(j−1,j) + (Q(t)/2)σy(j−1,j) ]

where the quadrature envelope is defined as:
Q(t) = −β (dI(t)/dt) / α

Leakage and seepage rates (L1 and L2) quantify population loss and recovery between computational and leakage subspaces:

L1 = (1/d1) Tr[I2 Ur I1 Ur†]
L2 = 1 − (1/d2) Tr[I2 Ur I2 Ur†]

1. Clone the repository:
   ```bash
   git clone https://github.com/uday-0702/IWQT-Conference-Poster.git
   cd IWQT-Conference-Poster
# Citation
@article{fast,
  author = {E. Hyyppä and others},
  title = {Reducing Leakage of Single-Qubit Gates for Superconducting Quantum Processors Using Analytical Control Pulse Envelopes},
  journal = {Phys. Rev. Applied},
  year = {2024},
  volume = {22},
  pages = {024034},
}

