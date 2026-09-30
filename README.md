# Quantum annealing Hamiltonian explorer

An interactive page for exploring the time-dependent quantum annealing Hamiltonian

H(s) = −A(s)/2 Σᵢ σˣᵢ + B(s)/2 ( Σᵢ hᵢ σᶻᵢ + Σ₍ᵢ,ⱼ₎∈E Jᵢⱼ σᶻᵢ σᶻⱼ )

on a spin graph of up to 9 spins.

**Live demo:** https://romeronatalia.github.io/quantum-annealing-hamiltonian-explorer/

## Spin graphs

- **Networks:** complete graph, star, random (Erdős–Rényi, edge probability p), and the 8-qubit Chimera unit cell K₄,₄.
- **Lattices:** 1D chain, 2D square, and 2D triangular, with open or periodic boundaries.
- **Couplings:** the same J on every edge, or random ±J (a spin glass).

The spin-graph panel shows the ground state ψ₀(s) at the current s. Each spin is drawn as its Bloch vector (⟨σˣ⟩, ⟨σᶻ⟩), and each bond is colored green if it is satisfied or red if it is frustrated. Press Play to watch the spins turn from the driver direction toward the classical solution.

## Plots

- The schedules A(s) and B(s).
- The lowest energy levels, with the minimum gap marked.
- The gap Δ(s) compared with thermal energy k_BT/h.
- Ground-state probabilities over classical configurations.

## Numerics

Up to 6 spins, each point uses exact dense diagonalization. From 7 spins on, a restarted block-Krylov (Rayleigh–Ritz) solver finds the lowest levels to a residual below 10⁻⁴ GHz, and golden-section search refines the minimum gap. Everything runs in a Web Worker, so the controls stay responsive.

To run it locally, open `index.html` in a browser. It has no build step.
