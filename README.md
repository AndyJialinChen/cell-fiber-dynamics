# cell-fiber-dynamics
Phase Difference Dynamics of an Actin Polymerization Cell–Fiber System: Numerical Analysis and Steady State Timing Investigation

# Cell–Fiber Phase-Difference Dynamics

Repository for the paper

> **Phase Difference Dynamics of an Actin Polymerization Cell–Fiber System**  
> Jialin Chen, Alex Mogilner, Wenzheng Shi (2025)

It contains every script, dataset, and executed notebook used to verify
the model’s five empirical conclusions (**C1 – C5**) and to benchmark the
trimmed-harmonic time-to-steady estimator.

---

## Scientific snapshot

We model an **elliptical cell** (orientation \(\Psi\)) enclosing a **radial
fiber** (orientation \(\Theta\)).  A geometry-constrained torque balance
reduces the system to two ODEs; subtracting yields a one-dimensional
autonomous equation

$$
\[
\dot{\delta}=f(\delta),\qquad\delta=\Psi-\Theta,
\]
$$

whose \(\pi\)-periodic structure governs all dynamics.

Large numerical sweeps (~10⁴ trajectories) reveal:

| ID | Robust property | Verified in |
|----|-----------------|-------------|
| **C1** | Steady state ⇔ \(f\) has zeros | `numerical conclusion verify/` |
| **C2** | Sign \(f(\delta_0)\) picks the target zero | `chirality dynamics/` |
| **C3** | Pre-steady motion is strictly monotone | `numerical conclusion verify/` |
| **C4** | Post-steady drift is negligible | `numerical conclusion verify/` |
| **C5** | Convergence stops at the first zero met | `numerical conclusion verify/` |

From these we derive a **trimmed-harmonic** estimate

$$
T_{\text{steady}}
  = \int_{\min(\delta_0,\delta_*)}^{\max(\delta_0,\delta_*)}
      \frac{d\delta}{\lvert f(\delta) \rvert}
  \qquad\text{(trim }5\times10^{-4}\text{ rad)}
$$


which attains **0.24 % median error** across 11 130 random parameter sets.
