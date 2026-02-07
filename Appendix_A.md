# Appendix A. Lagrange Equation for Nominal and Detailed Plant

## Introduction

This page provides the detailed derivations of the Lagrange equation corresponding to Eq. (18) for the **nominal** and **detailed** plant presented in the paper.

---

## Lagrange Equation

In Eq. (18) of the paper, the Lagrange equation is expressed in the form $$\mathbf{M}\ddot{\mathbf{q}} + \mathbf{C} + \mathbf{G} = \mathbf{B}\mathbf{u}$$:

$$
\begin{bmatrix}
M_{11} & 0 & 0 & M_{14} \\
0 & M_{22} & 0 & 0 \\
0 & 0 & M_{33} & 0 \\
M_{41} & 0 & 0 & M_{44}
\end{bmatrix}
\begin{bmatrix}
\ddot{\phi_x} \\ 
\ddot{\phi_y} \\ 
\ddot{\theta} \\ 
\ddot{\psi}
\end{bmatrix}
+
\begin{bmatrix}
C_1 \\ 
0 \\ 
C_3 \\ 
C_4
\end{bmatrix}
+
\begin{bmatrix}
G_1 \\ 
0 \\ 
G_3 \\ 
G_4
\end{bmatrix}
= \begin{bmatrix}
\frac{1}{2} & \frac{1}{2} & 0 \\
0 & 0 & 1 \\
-\frac{R}{W} & \frac{R}{W} & 0 \\
-\frac{1}{2} & -\frac{1}{2} & 0
\end{bmatrix}
\begin{bmatrix}
\tau_{xl} \\ 
\tau_{xr} \\ 
\tau_{y}
\end{bmatrix}
$$

## Nominal Plant

For the nominal plant, Eq. (18) is expressed as follows:

$$
\begin{cases}
M_{11} &= (2m + M)R^2 + 2I_w \\
M_{14} &= M_{41} = MRl\cos(\psi) \\
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
G_1 &= 0 \\
G_3 &= 0 \\
G_4 &= -Mgl \sin(\psi)
\end{cases}
$$

## Detailed Plant

In the detailed plant, $$\dot{x}$$, $$\dot{\theta}_a$$, and $$\dot{\alpha}$$ obtained using Eq. (11) can be converted to the form for $$\dot{\phi}_x$$ and $$\dot{\theta}$$ as follows:

$$
\dot{k} = k_{dl} \dot{\phi}\_{xl} + k_{dr} \dot{\phi}\_{xr} = k_{dx} \dot{\phi}\_{x} + k_{d\theta} \dot{\theta}\ = (k_{dl}+k_{dr}) \dot{\phi}\_x + \left( -\dfrac{W}{2R} k_{dl}+\dfrac{W}{2R} k_{dr} \right) \dot{\theta}\ \quad \text{for }\ k \in \\{x, \theta_a, \alpha \\} 
$$

Based on the ground contact modes of the omnidirectional wheel defined in **Section** 2, the z-direction motions of the left and right wheels, $$z_{wl}$$ and $$z_{wr}$$, can be defined as follows:

$$
z_{wl}=
\begin{cases}
R \quad \text{(Rolling Mode)} \\
R \cos(\left( \bar{\phi}_{xl} \pm \dfrac{\pi}{2N} \right) \quad \text{(Falling Mode)}
\end{cases}
$$

$$
z_{wr}=
\begin{cases}
R \quad \text{(Rolling Mode)} \\
R \cos(\left( \bar{\phi}_{xr} \pm \dfrac{\pi}{2N} \right) \quad \text{(Falling Mode)}
\end{cases}
$$

As $z_m=\frac{z_{wl} + z_{wr}}{2}$, $$\dot{z}_m$$ also can be converted to the form for $$\dot{\phi}_x$$ and $$\dot{\theta}$$ as follows:

$$
\dot{z}\_{m} = z_{m,dl} \dot{\phi}\_{xl} + z_{m,dr} \dot{\phi}\_{xr} = z_{m,dx} \dot{\phi}\_{x} + z_{m,d\theta} \dot{\theta}
$$

Thus, for the actual plant, Eq. (18) is expressed as follows:

$$
\begin{cases}
M_{11} &= 2a_{\phi_x} + 2I_w \\  
M_{14} &= M_{41} = b_1 x_{dx} + b_3 \z_{m,dx} \\
M_{22} &= 2a_2 \\  
M_{33} &= 2a_{\theta} + \dfrac{1}{2R^2}I_w W^2 + I_{\theta}  \\
M_{44} &=  2a_5 + I_{\psi} = Ml^2  + I_{\psi} \\  
\end{cases}
$$

$$
\begin{cases}
C_1 &= 2 \dot{a}\_{\phi_x} \dot{\phi}\_x + (\dot{b_1} x_{dx} + b_1 \dot{x}\_{dx} + \dot{b_3}\z_{m,dx} + b_3 \dot{\z}\_{m,dx} ) \dot{\psi} - \dfrac{\partial}{\partial \phi_x} (a_{\phi_x}) \dot{\phi}\_x^2 - \dfrac{\partial}{\partial \phi_x} (a_{\theta}) \dot{\theta}^2 - \left(b_1 \dfrac{\partial}{\partial\phi_x}(x_{dx}) + \dfrac{\partial}{\partial\phi_x}(b_3) \z_{m,dx} + b_3 \dfrac{\partial}{\partial\phi_x}(\z_{m,dx}) \right) \dot{\phi}\_x \dot{\psi} \\
C_3 &= 2 \dot{a}\_{\theta} \dot{\theta} - \dfrac{\partial}{\partial \theta} (a_{\phi_x})\dot{\phi}\_x^2 - \dfrac{\partial}{\partial \theta} (a_{\theta}) \dot{\theta}^2 - \left(b_1 \dfrac{\partial}{\partial\theta}(x_{dx}) + \dfrac{\partial}{\partial\theta}(b_3) \z_{m,dx} + b_3 \dfrac{\partial}{\partial\theta}(\z_{m,dx}) \right) \dot{\phi}\_x \dot{\psi} \\
C_4 &= (\dot{b_1} x_{dx} + b_1 \dot{x}\_{dx} + \dot{b_3}\z_{m,dx} + b_3 \dot{\z}\_{m,dx} ) \dot{\phi}\_x - \left(\dfrac{\partial}{\partial \psi} (b_1) x_{dx} + \dfrac{\partial}{\partial \psi} (b_3) \z_{m,dx} \right) \dot{\phi}_x \dot{\psi} \\
G_1 &= \dfrac{\partial U}{\partial\phi_x} = (2m+M) g \left( -R \sin(\alpha) + \dfrac{W}{2} \cos(\alpha)\right) \dfrac{\partial}{\partial\phi_x} (\alpha) \\
G_3 &= \dfrac{\partial U}{\partial\theta} = (2m+M) g \left( -R \sin(\alpha) + \dfrac{W}{2} \cos(\alpha)\right) \dfrac{\partial}{\partial\theta} (\alpha) \\
G_4 &= \dfrac{\partial U}{\partial\psi} = -Mgl\sin(\psi) 
\end{cases}
$$

where

$$
\begin{cases}
a_1 &= m + \dfrac{1}{2}M \\
a_2 &= \left(m + \dfrac{1}{2}M \right)r^2n_r^2 \\
a_2 &= \left(m + \dfrac{1}{2}M \right)r^2 \\
a_4 &= \dfrac{mW^2}{4} + \dfrac{1}{2}Ml^2\sin^2(\psi) \\
a_5 &= \dfrac{1}{2} m W^2 \cos^2(\alpha) + \dfrac{1}{8} M W^2 \cos^2(\alpha) \\
a_5 &= \dfrac{1}{2}Ml^2 \\
a_{\phi_x} &= a_1 x_{dx}^2 + a_2 + a_4 \theta_{dx}^2 + a_5 \alpha_{dx}^2 \\ T phi x
a_{\theta} &= a_1 x_{d\theta}^2 + a_4 \theta_{d\theta}^2 + a_5 \alpha_{d\theta}^2     T theta
\end{cases}
$$

$$
\begin{cases}
b_1 &=  Ml \cos(\psi)  \\
b_2 &= \left(2m + M \right)r^2n_r \\
b_3 &= Mrln_r \sin(\psi) \\
b_4 &= Mrl \sin(\psi) \\
b_5 &= -\dfrac{1}{2} MWl \cos(\alpha) \sin(\psi)
\end{cases}
$$
