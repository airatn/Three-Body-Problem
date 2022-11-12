# Cerebellar architecture in solving the Three-body problem
The three-body problem in celestial mechanics is the problem of determining the initial positions and velocities of three material mass points and solving their subsequent motion. There is no general solution to this problem in closed form, and numerical methods are required [1]. The general threebody problem is described by a system of second-order ordinary differential equations:

$$\begin{cases}
  \ddot q_1 = G\cdot m_2\frac{q_2-q_1}{|q_2-q_1|^3} + m_3\frac{q_3-q_1}{|q_3-q_1|^3}\\
  \ddot q_2 = G\cdot m_1\frac{q_1-q_2}{|q_1-q_2|^3} + m_3\frac{q_3-q_2}{|q_3-q_2|^3}\\
  \ddot q_3 = G\cdot m_1\frac{q_1-q_3}{|q_1-q_3|^3} + m_2\frac{q_2-q_3}{|q_2-q_3|^3}
\end{cases}$$

Here $q_i = (x_i, y_i, z_i)$ – point position vector, $m_i$ – mass of each point, $G$ – gravitational constant, $i = 1, 2, 3$. As a result, we get a set of nine second-order differential equations for point coordinates. Since there is no general closed-form solution, there is no analytical solution expressed in terms of a finite number of standard mathematical operations. At the same time, mathematical models make it possible to predict the movement of three bodies by computational methods. Below is a computational model configured to solve this problem.

For simplicity of presentation, consider the model when $z_i = 0, \dot z_i = 0, i = 1, 2, 3$. That is, the movement of all three bodies occurs in the same $XY$ plane. The system is then reduced to six differential equations. Let us show all the stages of creating a three-body problem model based on the proposed architecture.

1. Initially, we will form phase spaces from 22 components. This is a parametric space of 18 components $x_1, \dot x_1, \ddot x_1, . . . , y_3, \dot y_3, \ddot y_3$, and also 4 constants $m_1,m_2,m_3, G$. In the model, each of these parameters will correspond to a parallel fiber and a granule cell, either repeating the values of the input parameter, or additionally accumulating a value, that is, acting as an integrator. We illustrate this in Figure 1.

<img src="https://drive.google.com/uc?export=view&id=1P0crGaDgknBNXIXbSnQdwR2Dlee3H7kB" width="600">

<img src="https://drive.google.com/uc?export=view&id=1ctIOQH2_dxw8K8pySYui6veXVqlaDepl" width="700">

<img src="https://drive.google.com/uc?export=view&id=1_MhUFphKUgAlQkyVJpCiuRcqwkzTozwx" width="600">

<img src="https://drive.google.com/uc?export=view&id=1sRnavtkoQCpZoJBfeJW8kKnhINCp1IoP" width="600">

[1] J. Barrow-Green,Poincare and the Three Body Problem. (American Math. Soc., Providence, R.I., 1997).
[2] https://pyglet.readthedocs.io/en/latest/ . Accessed 2022.
[3] A. Chenciner and R. Montgomery, “A Remarkable Periodic Solution of the Three-Body Problem in the Case of Equal Masses,”arxiv.org (2000), https://doi.org/10.48550/arXiv.math/0011268, https://arxiv.org/abs/math/0011268
