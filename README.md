<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <!-- Include MathJax for LaTeX rendering -->
</head>
<body>
    <h1>POSTER — ANALYSIS OF LEAKAGE SUPPRESSION IN TRANSMON QUBITS UNDER DIFFERENT DRAG DRIVES</h1>

<p>This repository contains the poster presented at the International Workshop on Quantum Technology (IWQT) 2025, focused on the analysis of leakage suppression techniques in multilevel superconducting transmon qubits.</p>

<hr>

<h2>OVERVIEW</h2>
    <p>Superconducting transmon qubits — the workhorses of modern quantum processors — suffer from low anharmonicity and frequency crowding <p>(\(|\alpha / 2\pi| \in [150, 300] \, \text{MHz}\))</p>, which often leads to spectral overlap of control pulses with higher transitions such as $$\(|1\rangle \leftrightarrow |2\rangle\).$$ This overlap causes leakage errors, which are a major limitation in achieving high-fidelity quantum gates.</p>
    
<p>This work presents a comparative simulation and analysis of several DRAG-based pulse-shaping techniques that suppress leakage while maintaining fast and high-fidelity single-qubit gates.</p>

<hr>

<h2>METHODS</h2>
    <p>The following drive schemes were simulated and compared within a three-level transmon model for an X-gate implementation:</p>
    <ul>
        <li>Standard DRAG</li>
        <li>Fifth-Order DRAG (with time-dependent detuning)</li>
        <li>FAST DRAG — Fourier Ansatz Spectrum Tuning</li>
        <li>HD DRAG — Higher Derivative DRAG</li>
    </ul>

<p>The rotating-frame Hamiltonian used for analysis is given by:</p>

<div style="text-align:center;">
        <p>
            $$ H_R = \sum_j \left( \delta_j |j\rangle \langle j| + \frac{I(t)}{2} \sigma_x^{j-1,j} + \frac{Q(t)}{2} \sigma_y^{j-1,j} \right) $$
        </p>
    </div>

<p>where the quadrature envelope is defined as:</p>

<div style="text-align:center;">
        <p>
            $$ Q(t) = -\beta \frac{dI(t)}{dt} \frac{1}{\alpha} $$
        </p>
    </div>

<p>Leakage and seepage rates (\(L_1\) and \(L_2\)) quantify population loss and recovery between computational and leakage subspaces:</p>

<div style="text-align:center;">
        <p>
            $$ L_1 = \frac{1}{d_1} \text{Tr}\left[ I_2 U_r I_1 U_r^\dagger \right] $$
        </p>
        <p>
            $$ L_2 = 1 - \frac{1}{d_2} \text{Tr}\left[ I_2 U_r I_2 U_r^\dagger \right] $$
        </p>
    </div>

<hr>

<h2>KEY FINDINGS</h2>
    <ul>
        <li><strong>Leakage Suppression:</strong> Both <strong>FAST DRAG</strong> and <strong>HD DRAG</strong> significantly reduce leakage around the qubit anharmonic frequency (\( \alpha / 2\pi = -212~\mathrm{MHz} \)).</li>
        <li><strong>Spectral Optimization (FAST DRAG):</strong> Provides enhanced suppression bandwidth and tunable spectral control using Fourier coefficients (\( \{A_n\} \)).</li>
        <li><strong>Higher Derivative Expansion (HD DRAG):</strong> Incorporates up to second-order derivatives in \(I(t)\) and third-order in \(Q(t)\), achieving leakage suppression without explicit spectral optimization.</li>
    </ul>

<div style="text-align:center;">
        <p>
            $$ I(t) = A \left[ \Omega_I(t) + \beta^2 \ddot{\Omega}_I(t) \right] $$
        </p>
        <p>
            $$ Q(t) = -A \frac{\beta}{\alpha} \left[ \dot{\Omega}_I(t) + \beta^2 \dddot{\Omega}_I(t) \right] $$
        </p>
    </div>

<ul>
        <li><strong>Phase Error Sensitivity:</strong> The average gate fidelity is more sensitive to phase accumulation errors than to leakage itself.</li>
        <li><strong>Bandwidth Control:</strong> <strong>FAST DRAG</strong> exhibits the widest suppression bandwidth, providing superior control for multilevel systems.</li>
    </ul>

<hr>

<h2>COLLABORATION</h2>
    <p>This research is a collaborative effort between:</p>
    <ul>
        <li><strong>Department of Physics, Indian Institute of Technology (BHU), Varanasi, India</strong></li>
        <li><strong>Nuclear Physics Division, Bhabha Atomic Research Centre (BARC), Mumbai, India</strong></li>
    </ul>

<p><strong>Contributors:</strong></p>
    <ul>
        <li>Uday Mathur — IIT (BHU)</li>
        <li>Dr. Sandeep Joshi — BARC</li>
        <li>Dr. Prashant Shukla — BARC</li>
    </ul>

<hr>

<h2>TAKEAWAYS</h2>
    <ul>
        <li><strong>FAST DRAG:</strong> Provides flexible and high-fidelity control with enhanced spectral suppression.</li>
        <li><strong>HD DRAG:</strong> Offers simplicity and low calibration overhead while maintaining robustness.</li>
        <li>Gate fidelity is limited primarily by phase errors rather than leakage errors.</li>
    </ul>

<hr>

<h2>SETUP INSTRUCTIONS</h2>
    <ol>
        <li>Clone the repository:
            <pre><code>git clone https://github.com/uday-0702/IWQT-Conference-Poster.git
cd IWQT-Conference-Poster</code></pre>
        </li>
        <li>Open the poster file:
            <p>The poster is available as "<strong>IWQT-poster-Uday-Mathur.pdf</strong>". You can view it using any standard PDF viewer.</p>
        </li>
    </ol>

<hr>

<h2>CONTACT</h2>
    <ul>
        <li><strong>Uday Mathur</strong> — uday.mathur.cd.phy22@itbhu.ac.in</li>
        <li><strong>Prashant Shukla</strong> — pshuklabarc@gmail.com</li>
    </ul>

<hr>

<h2>REFERENCE</h2>
    <p>[1] E. Hyyppä et al., “Reducing Leakage of Single-Qubit Gates for Superconducting Quantum Processors Using Analytical Control Pulse Envelopes,” <i>Physical Review Applied</i>, Vol. 22, 024034 (2024).</p>

<hr>

<h2>CITATION</h2>
    <pre><code>
@article{fast_drag_2024,
  author  = {E. Hyyppä and others},
  title   = {Reducing Leakage of Single-Qubit Gates for Superconducting Quantum Processors Using Analytical Control Pulse Envelopes},
  journal = {Physical Review Applied},
  year    = {2024},
  volume  = {22},
  pages   = {024034},
}
</code></pre>

<hr>

<h2>PRESENTATION DETAILS</h2>
    <p>Presented at the <strong>International Workshop on Quantum Technology (IWQT) 2025</strong>.</p>
    <p>In collaboration with the <strong>Bhabha Atomic Research Centre (BARC)</strong> and the <strong>Indian Institute of Technology (BHU), Varanasi</strong>.</p>

</body>
</html>
