# Appendix B. Reference Trajeectory and Disturbance in Simulation
## Introduction

This page provides the detailed derivations of the reference trajectories and external disturabance input to the simulation presented in the paper.

---

## Reference Trajeectory

In Eq. (22) of the paper, the Lagrange equation is expressed in the form $$\mathbf{M}\ddot{\mathbf{q}} + \mathbf{C} + \mathbf{G} = \mathbf{B}\mathbf{u}$$:

$$
x_{\mathrm{tri}}(t) =
\left{
\begin{cases}
&- 0.4 + \frac{0.8}{6.5}t \enspace (0 \le t < 6.5)  \\
& 0.4 - \frac{0.4}{6.5} (t - 6.5) \enspace (6.5 \le t < 13.0) \\
& - \frac{0.4}{6.5} (t - 13.0) \enspace (13.0 \le t < 19.5) \\
& -0.4 \quad (\text{Otherwise})
\right.
\end{cases}
$$

$$
y_{\mathrm{tri}}(t) =
\left{
\begin{cases}
&- 0.4 \enspace (0 \le t < 6.5)  \\
&-0.4 + \frac{\sqrt{3} \cdot 0.4}{6.5} (t - 6.5) \enspace (6.5 \le t < 13.0) \\
& 0.4 - \frac{\sqrt{3} \cdot 0.4}{6.5} (t - 13.0) \enspace (13.0 \le t < 19.5) \\
& -0.4 \quad (\text{Otherwise})
\right.
\end{cases}
$$

$$
x_{\mathrm{cir}}(t) =
\left\{
\begin{cases}
& 0.5\cos\left(\frac{2 \pi t}{20.0}\right) \enspace (0 \le t < 20.0)  \\
& 0.5 \quad (\text{Otherwise})
\right.
\end{cases}
$$

$$
y_{\mathrm{cir}}(t) =
\left\{
\begin{cases}
& 0.5\sin\left(\frac{2 \pi t}{20.0}\right) \enspace (0 \le t < 20.0)  \\
& 0 \quad (\text{Otherwise})
\right.
\end{cases}
$$

## Nominal Plant

For the nominal plant, Eq. (22) is expressed as follows:

$$
\begin{cases}
M_{11} &= (2m + M)(R^2 + r^2 n_r^2) + 2I_w \\
M_{14} &= M_{41} = MRl\cos(\psi) \\
M_{21} &= \left( m + \dfrac{1}{2}M \right) r^2 n_r \\
M_{22} &= (2m + M) r^2 \\
M_{33} &= \dfrac{mW^2}{2} + Ml^2 \sin^2(\psi) + \dfrac{1}{2R^2} I_w W^2 + I_\theta \\
M_{44} &= Ml^2 + I_\psi
\end{cases}
$$

$$
\begin{cases}
C_1 &= -MRl \sin(\psi) \dot{\psi}^2 \\
C_3 &= 2Ml^2 \sin(\psi)\cos(\psi)\dot{\theta}\dot{\psi} \\
C_4 &= 0 \\
G_4 &= -Mgl \sin(\psi)
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
