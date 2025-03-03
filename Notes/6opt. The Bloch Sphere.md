---
dg-publish: true
---
#Notes 

The density operators of single qubits have a particularly nice geometric representation, known as the **Bloch sphere**.

Consider some arbitrary (pure) quantum state, which can *always* be written as 

$$
|\psi \rangle =e^{i\alpha}\left( \cos\left( \frac{\theta}{2} \right)|0\rangle +e^{i\phi}\sin\left( \frac{\theta}{2} \right)|1\rangle  \right)
$$

where we have chosen to write the amplitude of $|0\rangle$ as $e^{i\alpha}\cos \frac{\theta}{2}$ and the amplitude of $|1\rangle$ as $e^{i(\alpha+\phi)}\sin \frac{\theta}{2}$. 

The density matrix of this state, in the standard basis, is 

$$
\rho=|\psi \rangle \langle \psi|=\begin{pmatrix}
\cos^{2}\left( \frac{\theta}{2} \right) & e^{-i\phi}\cos \left( \frac{\theta}{2} \right)\sin\left( \frac{\theta}{2} \right) \\
e^{i\phi}\cos \left( \frac{\theta}{2} \right)\sin\left( \frac{\theta}{2} \right) & \sin^{2}\left( \frac{\theta}{2} \right)
\end{pmatrix}
$$

which is notably *independent of $\alpha$* (the global phase).

Using double angle formulas and Euler's formula:

$$
\begin{align}
\cos \theta&=2\cos^{2}\left( \frac{\theta}{2} \right)-1=1-2\sin^{2}\left( \frac{\theta}{2} \right) \\ 

\sin \theta&=2\sin\left( \frac{\theta}{2} \right)\cos \left( \frac{\theta}{2} \right) \\
 
e^{i\phi}&= \cos(\phi)+i\sin(\phi)
\end{align}
$$

we can see that $\rho$ can be written as

$$
\begin{align}
\rho&=\begin{pmatrix}
\cos^{2}\left( \frac{\theta}{2} \right) & e^{-i\phi}\cos \left( \frac{\theta}{2} \right)\sin\left( \frac{\theta}{2} \right) \\
e^{i\phi}\cos \left( \frac{\theta}{2} \right)\sin\left( \frac{\theta}{2} \right) & \sin^{2}\left( \frac{\theta}{2} \right)
\end{pmatrix} \\
 \\
&=\frac{1}{2} \begin{pmatrix}
1+\cos \theta  & (\cos \phi-i\sin \phi)\sin \theta \\
(\cos \phi+i\sin \phi)\sin \theta  & 1-\cos \theta
\end{pmatrix} \\
 \\
&=\frac{1}{2}\left[\begin{pmatrix}
1&0 \\
0 & 1
\end{pmatrix}+\cos \phi \sin \theta \begin{pmatrix}
0 & 1 \\
1 & 0
\end{pmatrix} +\sin \phi \sin \theta \begin{pmatrix}
0 & -i \\
i & 0
\end{pmatrix} +\cos \theta \begin{pmatrix}
1 & 0 \\
0 & -1
\end{pmatrix}\right] \\
 \\
&= \frac{1}{2}[I+(\sin \theta \cos \phi)X+(\sin \theta \sin \phi)Y+(\cos \theta)Z ] \\
 \\
&= \frac{1}{2}(I+\hat{\boldsymbol{n}}\cdot\boldsymbol{\sigma})
\end{align}
$$

where in the final line, we define the **Bloch vector**

$$
\hat{\boldsymbol{n}}=\begin{bmatrix}
\sin \theta \cos \phi \\
\sin \theta \sin \phi \\
\cos \theta
\end{bmatrix}
$$

which is a unit vector in three dimensions, pointing in the direction $\theta,\phi$ in spherical polar coordinates, and $\boldsymbol{\sigma}=(X,Y,Z)$ is a vector of Pauli operators.

This shows that the density operator of a pure qubit can be represented by the Bloch vector $\hat{\boldsymbol{n}}$. We say that this $\hat{\boldsymbol{n}}$ is the **Bloch vector representation of a qubit**. 

Since $\hat{\boldsymbol{n}}$ is a unit vector, pure states of different qubits all lie on the surface of a sphere of radius 1, known as the **Bloch sphere**. What this means is that the *entire surface of the sphere corresponds to pure quantum states*.

![[Screenshot 2025-02-22 at 18.36.30.png]]

Arbitrary density operators, like $\rho$ above (including mixed states), can also be represented by Bloch vectors. In particular, consider the mixed state

$$
\rho=\sum_{k}p_{k}|\psi_{k}\rangle \langle \psi_{k}|
$$

Since each pure state $|\psi_{k}\rangle \langle\psi_{k}|$ can be written as 

$$
|\psi_{k}\rangle \langle \psi_{k}|=\frac{1}{2}(I+\hat{\boldsymbol{n}}^{(k)} \cdot\boldsymbol{\sigma})
$$

then it follows that

$$
\begin{align}
\rho & = \sum_{k}p_{k}|\psi_{k}\rangle \langle \psi_{k}| \\
 & = \frac{1}{2}\sum_{k}p_{k}(I+\hat{\boldsymbol{n}}^{(k)} \cdot  \boldsymbol{\sigma}) \\
 & = \frac{1}{2}\left( I+\left( \sum_{k}p_{k} \hat{\boldsymbol{n}}^{(k)} \right)\cdot  \boldsymbol{\sigma} \right)
 \\
 & = \frac{1}{2}(I+\boldsymbol{n}\cdot  \boldsymbol{\sigma})
\end{align}
$$

where we define the **average Bloch vector** $\boldsymbol{n}=\sum_{k}p_{k}\hat{\boldsymbol{n}}^{(k)}$, which is the average of the Bloch vectors of the pure states in the decomposition of the density operator. 

We should notice now that

$$
\begin{align}
\boldsymbol{n}\cdot  \boldsymbol{n}  & = \sum_{kl}p_{k}p_{l}\hat{\boldsymbol{n}}^{(k)}\cdot  \hat{\boldsymbol{n}}^{(l)} \leq \sum_{kl}p_{k}p_{l}=1
\end{align}
$$

> [!help] Scalar products of unit vectors
> The scalar product here must always be either one or less than one, since these are unit vectors.

That is, the Bloch vector $\boldsymbol{n}$ of a density operator $\rho$ is never longer than a unit vector, but in general can be shorter. That is - these vectors are *in general* inside the unit/Bloch sphere. It can be shown that the equality can never be reached if the state is mixed [link problem sheet]. We conclude therefore that 
- density operators corresponding to *mixed states* lie on the interior of the sphere
- density operators corresponding to *pure states* lie on the surface of the sphere
It can also be shown that *any* vector $\boldsymbol{n}$ inside the Bloch sphere corresponds to a *valid density operator*. In other words, the space of qubits is in one-to-one correspondence with the set of Bloch vectors, which is given by the unit sphere in $\mathbb{R}^3$.

An interesting limiting case is that of the maximally mixed state:

$$
\rho=\frac{1}{2}I=\frac{1}{2} |0\rangle \langle 0|+\frac{1}{2}|1\rangle \langle 1|
$$

The Bloch vector is $\boldsymbol{n}=[0,0,0]$ i.e. the center of the Bloch sphere. 

There is a quick method to calculate the Bloch vector from a given density operator. We can say that

$$
\boldsymbol{n}=\begin{bmatrix}
\text{tr} (X\rho) \\
\text{tr} (Y\rho) \\
\text{tr} (Z\rho)
\end{bmatrix}
$$

To see this, consider just $n_{x}$. 

$$
\begin{align}
\text{tr} (X\rho) & =\text{tr} \left( X \frac{1}{2}(I+\boldsymbol{n}\cdot  \boldsymbol{\sigma}) \right) \\
 & = \text{tr} \left( X \frac{1}{2} (I+n_{x}X+n_{y}Y+n_{z}Z) \right) \\
 & = \frac{1}{2} (\text{tr} X+n_{x}\text{tr} X^{2}+n_{y}\text{tr}  (XY) +n_{z}\text{tr} (XZ)) \\
 & = n_{x}
\end{align}
$$

> [!help] Trace operations
> It is useful to note here that 
> $$\text{tr} X=\text{tr} (|0\rangle \langle 1|+|1\rangle \langle 0|)=\text{tr} (|0\rangle \langle 1|)+\text{tr} (|1\rangle \langle 0|)=\langle 1|0\rangle +\langle 0|1\rangle =0$$
>and so on for the other traces.

Similar operations can be shown for $n_{y}$ and $n_{z}$. Thus, the components of the Bloch vector are *precisely* the expectation values of the three Pauli spin observables in the state. 

One surprising and counter-intuitive property of the Bloch sphere representation is that *orthogonal pure quantum states* correspond to *opposite points on the surface of the Bloch sphere*! That is, if a pure quantum state $|\psi \rangle$ has a Bloch vector $\hat{\boldsymbol{n}}$, then the orthogonal state $|\psi^{\perp}\rangle$ (i.e. $\langle\psi^{\perp}|\psi \rangle=0$) has Bloch vector $\hat{\boldsymbol{n}}^{\perp}=-\hat{\boldsymbol{n}}$. Therefore, we see that

$$
\hat{\boldsymbol{n}}^{\perp}\cdot  \hat{\boldsymbol{n}}=-1
$$


> [!warning] Care with orthogonality
> It is clear from the above that orthogonality of quantum states is **not** the same as orthogonality of Bloch vectors (the two Bloch vectors above resulting from orthogonal states are not orthogonal).

Finally, if we consider applying a unitary transformation to an arbitrary qubit, we can ask what happens to the Bloch sphere - that is, we think about some mapping; what happens to all points on Bloch sphere if a unitary transformation is applied. As it turns out, applying a unitary transformation simply *rotates* the Bloch sphere. 
![[Screenshot 2025-02-25 at 13.17.59.png]]
Similarly, we can consider what a **measurement** looks like on a Bloch sphere. We find that it depends upon the projection of the Bloch vector along an axis (defined by measurement). For example, when measuring $Z$ on a qubit, the probability to obtain $+1$ is 

$$
P(+1)=\text{tr} (\rho|0\rangle \langle 0|)=\frac{1}{2}(1+n_{z})
$$