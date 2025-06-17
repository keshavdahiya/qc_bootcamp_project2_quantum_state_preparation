# Quantum State Preparation

(Erdös quantum computing bootcamp mini project 2)

Given a $2^n$-dimensional state vector $\psi=\sum_{x=0}^{2^n-1}\psi_x\ket{x}_n\in\mathbb{C}^{2^n}$ such that $\lVert\psi\rVert_2=1$, we write a function QSP $(\psi)$ which outputs a circuit $U$, such that 
$$U|0\rangle_n=\sum_{x=0}^{2^n-1}\psi_x\ket{x}_n\ .$$

The construction is done in three steps. 
1. Using the absolute values $|\psi_x|$, find angles $\theta, \theta_{0}, \theta_{1}, \theta_{00}, \theta_{10}, \theta_{01}, \theta_{11}, \cdots $ such that (for example in the case of $n=3$) 
$$\sum_{x=0}^{2^3-1}|\psi_x|\ket{x}_n=\cos(\theta/2)\bigg(\cos(\theta_{0}/2)\Big(\cos(\theta_{00}/2)\ket{0}+\sin(\theta_{00}/2)\ket{1}\Big)\ket{0}+\sin(\theta_{0}/2)\Big(\cos(\theta_{10}/2)\ket{0}+\sin(\theta_{10}/2)\ket{1}\Big)\ket{1}\bigg)\ket{0}$$
$$\qquad\qquad\qquad + \sin(\theta/2)\bigg(\cos(\theta_{1}/2)\Big(\cos(\theta_{01}/2)\ket{0}+\sin(\theta_{01}/2)\ket{1}\Big)\ket{0}+\sin(\theta_{1}/2)\Big(\cos(\theta_{11}/2)\ket{0}+\sin(\theta_{11}/2)\ket{1}\Big)\ket{1}\bigg)\ket{1}.$$ 
$\quad\ \ $ This step is entirely classical.

2. Using the $R_Y$ multiplexers and the angles obtained in step 1, prepare the state $\sum_{x=0}^{2^n-1}|\psi_x|\ket{x}_n$.

3. Using the $R_Z$ multiplexers and one ancilla, prepare the state $\sum_{x=0}^{2^n-1}\psi_x\ket{x}_n$ from the state $\sum_{x=0}^{2^n-1}|\psi_x|\ket{x}_n$.

The construction uses $O(n\,2^n)$ $1$-qubit gates, $O(2^n)$ multi-controlled $R_Z$-gates and one ancilla qubit. The circuit has a gate depth of $O(2^n)$.
