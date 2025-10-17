POSTER — ANALYSIS OF LEAKAGE SUPPRESSION IN TRANSMON QUBITS UNDER DIFFERENT DRAG DRIVES
=======================================================================================

This repository contains the poster presented at the International Workshop on Quantum Technology (IWQT) 2025, focused on the analysis of leakage suppression techniques in multilevel superconducting transmon qubits.

---------------------------------------------------------------------------------------
OVERVIEW
---------------------------------------------------------------------------------------

Superconducting transmon qubits — the workhorses of modern quantum processors — suffer from low anharmonicity and frequency crowding (|α/2π| ∈ [150, 300] MHz), which often leads to spectral overlap of control pulses with higher transitions such as |1⟩ ↔ |2⟩.
This overlap causes leakage errors, which are a major limitation in achieving high-fidelity quantum gates.

This work presents a comparative simulation and analysis of several DRAG-based pulse-shaping techniques that suppress leakage while maintaining fast and high-fidelity single-qubit gates.

---------------------------------------------------------------------------------------
METHODS
---------------------------------------------------------------------------------------

The following drive schemes were simulated and compared within a three-level transmon model for an X-gate implementation:

1. Standard DRAG
2. Fifth-Order DRAG (with time-dependent detuning)
3. FAST DRAG — Fourier Ansatz Spectrum Tuning
4. HD DRAG — Higher Derivative DRAG

The rotating-frame Hamiltonian used for analysis is given by:
$$
H_R = \( \sum_j ( \delta_j |j\rangle \langle j| + \frac{I(t)}{2}\sigma_x^{j-1,j} + \frac{Q(t)}{2}\sigma_y^{j-1,j} ) \)
$$
where the quadrature envelope is defined as:
$$Q(t) = \( -\beta \frac{dI(t)}{dt} \frac{1}{\alpha} \)$$

Leakage and seepage rates (L1 and L2) quantify population loss and recovery between computational and leakage subspaces:
$$
L1 = \( \frac{1}{d_1} \text{Tr}[ I_2 U_r I_1 U_r^\dagger ] \)
L2 = \( 1 - \frac{1}{d_2} \text{Tr}[ I_2 U_r I_2 U_r^\dagger ] \)
$$
---------------------------------------------------------------------------------------
KEY FINDINGS
---------------------------------------------------------------------------------------

• Leakage Suppression:
  Both FAST DRAG and HD DRAG significantly reduce leakage around the qubit anharmonic frequency (\( \alpha / 2\pi = -212~\mathrm{MHz} \)).

• Spectral Optimization (FAST DRAG):
  Provides enhanced suppression bandwidth and tunable spectral control using Fourier coefficients (\( \{A_n\} \)).

• Higher Derivative Expansion (HD DRAG):
  Incorporates up to second-order derivatives in I(t) and third-order in Q(t), achieving leakage suppression without explicit spectral optimization.
  $$
  I(t) = \( A [ \Omega_I(t) + \beta^2 \ddot{\Omega}_I(t) ] \)
  Q(t) = \( -A \frac{\beta}{\alpha} [ \dot{\Omega}_I(t) + \beta^2 \dddot{\Omega}_I(t) ] \)
  $$
• Phase Error Sensitivity:
  The average gate fidelity is more sensitive to phase accumulation errors than to leakage itself.

• Bandwidth Control:
  FAST DRAG exhibits the widest suppression bandwidth, providing superior control for multilevel systems.

---------------------------------------------------------------------------------------
COLLABORATION
---------------------------------------------------------------------------------------

This research is a collaborative effort between:

- Department of Physics, Indian Institute of Technology (BHU), Varanasi, India
- Nuclear Physics Division, Bhabha Atomic Research Centre (BARC), Mumbai, India

Contributors:
- Uday Mathur — IIT (BHU)
- Dr. Sandeep Joshi — BARC
- Dr. Prashant Shukla — BARC

---------------------------------------------------------------------------------------
TAKEAWAYS
---------------------------------------------------------------------------------------

- FAST DRAG provides flexible and high-fidelity control with enhanced spectral suppression.
- HD DRAG offers simplicity and low calibration overhead while maintaining robustness.
- Gate fidelity is limited primarily by phase errors rather than leakage errors.

---------------------------------------------------------------------------------------
SETUP INSTRUCTIONS
---------------------------------------------------------------------------------------

1. Clone the repository:
   git clone https://github.com/uday-0702/IWQT-Conference-Poster.git
   cd IWQT-Conference-Poster

2. Open the poster file:
   The poster is available as "IWQT-poster-Uday-Mathur.pdf".
   You can view it using any standard PDF viewer.

---------------------------------------------------------------------------------------
CONTACT
---------------------------------------------------------------------------------------

Uday Mathur — uday.mathur.cd.phy22@itbhu.ac.in
Prashant Shukla — pshuklabarc@gmail.com

---------------------------------------------------------------------------------------
REFERENCE
---------------------------------------------------------------------------------------

[1] E. Hyyppä et al.,
“Reducing Leakage of Single-Qubit Gates for Superconducting Quantum Processors Using Analytical Control Pulse Envelopes,”
Physical Review Applied, Vol. 22, 024034 (2024).

---------------------------------------------------------------------------------------
CITATION
---------------------------------------------------------------------------------------

@article{fast_drag_2024,
  author  = {E. Hyyppä and others},
  title   = {Reducing Leakage of Single-Qubit Gates for Superconducting Quantum Processors Using Analytical Control Pulse Envelopes},
  journal = {Physical Review Applied},
  year    = {2024},
  volume  = {22},
  pages   = {024034},
}

---------------------------------------------------------------------------------------
PRESENTATION DETAILS
---------------------------------------------------------------------------------------

Presented at the International Workshop on Quantum Technology (IWQT) 2025.
In collaboration with the Bhabha Atomic Research Centre (BARC) and the Indian Institute of Technology (BHU), Varanasi.
