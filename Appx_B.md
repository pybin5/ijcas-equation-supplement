# Appendix B. Reference Trajectory and Disturbance in Simulation

## Introduction

This page provides the detailed derivations of the reference trajectories and external disturabance input to the simulation presented in the paper.

---

## Reference Trajeectory

The $$x$$ and $$y$$ positions for the triangular and circular trajectories input to the simulation are represented as $$x_{\mathrm{tri}}(t)$$, $$y_{\mathrm{tri}}(t)$$, $$x_{\mathrm{cir}}(t)$$, and $$y_{\mathrm{cir}}(t)$$, respectively, as follows:

$$
x_{\mathrm{tri}}(t) =
\begin{cases}
&- 0.4 + \dfrac{0.8}{6.5}t \enspace (0 \le t < 6.5)  \\
& 0.4 - \dfrac{0.4}{6.5} (t - 6.5) \enspace (6.5 \le t < 13.0) \\
& - \dfrac{0.4}{6.5} (t - 13.0) \enspace (13.0 \le t < 19.5) \\
& -0.4 \quad (\text{Otherwise})
\end{cases}
$$

$$
y_{\mathrm{tri}}(t) =
\begin{cases}
&- 0.4 \enspace (0 \le t < 6.5)  \\
&-0.4 + \dfrac{\sqrt{3} \cdot 0.4}{6.5} (t - 6.5) \enspace (6.5 \le t < 13.0) \\
& 0.4 - \dfrac{\sqrt{3} \cdot 0.4}{6.5} (t - 13.0) \enspace (13.0 \le t < 19.5) \\
& -0.4 \quad (\text{Otherwise})
\end{cases}
$$

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


## External Disturbance

The impulse-type disturbances applied to the left and right wheels, $$\tau_{d,L}(t)$$ and $$\tau_{d,R}(t)$$, in the simulation are as follows:

$$
\begin{cases}
\tau_{d,L}(t) &= 10 \left[ u(t - 4) - u(t - 4.01) \right] + 16 \left[ u(t - 12) - u(t - 12.01) \right]   \\
\tau_{d,R}(t) &= 12 \left[ u(t - 7) - u(t - 7.01) \right] + 11 \left[ u(t - 15) - u(t - 15.01) \right]   \\
\end{cases}
$$

where $$u(t)$$ is the unit step function.
