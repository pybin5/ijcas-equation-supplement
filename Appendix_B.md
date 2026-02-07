# Appendix B. Reference Trajectory in Simulation

## Introduction

This page provides the detailed derivations of the reference trajectory input to the simulation presented in the paper.

---

## Reference Trajectory

The $$x$$ and $$y$$ positions for the circular trajectories input to the simulation are represented as $$x_{\mathrm{cir}}(t)$$ and $$y_{\mathrm{cir}}(t)$$, respectively, as follows:

$$
x_{\mathrm{cir}}(t) =
\begin{cases}
& 0.5\cos\left(\dfrac{2 \pi t}{20.0}\right) \enspace (0 \le t < 20.0)  \\
& 0.5 \quad (\text{Otherwise})
\end{cases}
$$

$$
y_{\mathrm{cir}}(t) =
\begin{cases}
& 0.5\sin\left(\dfrac{2 \pi t}{20.0}\right) \enspace (0 \le t < 20.0)  \\
& 0 \quad (\text{Otherwise})
\end{cases}
$$

