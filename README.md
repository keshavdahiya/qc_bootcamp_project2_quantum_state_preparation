# Quantum State Preparation

(Erdös quantum computing bootcamp mini project 2)

Given a $2^n$-dimensional state vector $\psi=\sum_{x=0}^{2^n-1}\psi_x|x\rangle_n\in\mathbb{C}^{2^n}$ such that $\lVert \psi \rVert_2=1$, we write a function QSP $(\psi)$ which outputs a circuit $U$, such that 
$$U|0\rangle = \psi .$$

The construction is done in two steps. 

1. Using the $R_Y$ multiplexers, prepare the state $\sum_{x=0}^{2^n-1}|\psi_x|\ |x\rangle_n$.

2. Using the $R_Z$ multiplexers and one ancilla, prepare the state $\sum_{x=0}^{2^n-1}\psi_x\ |x\rangle_n$ from the state $\sum_{x=0}^{2^n-1}|\psi_x|\ |x\rangle_n$.

The construction uses $O(n 2^n)$ $1$-qubit gates, $O(2^n)$ multi-controlled $R_Z$-gates and one ancilla qubit. The circuit has a gate depth of $O(2^n)$.
