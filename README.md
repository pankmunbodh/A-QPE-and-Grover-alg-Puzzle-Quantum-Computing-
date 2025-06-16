This notebook solves the following problem:

We will write a function that takes as input an $n$-qubit unitary, that is, $U|\psi\rangle_n = e^{2 \pi i \theta(\psi)}|\psi\rangle_n$ such that all values of $e^{2 \pi i \theta(\psi)}$ are distinct. We will assume that:

1. There exists a number $d \in \mathbb{Z}_+$ such that $2^d\theta(\psi) \in \mathbb{Z}$.
2. There exists a unique $x \in \mathbb{F}_2^n$ such that $e^{2\pi i \theta(\psi)} = e^{2\pi i t}$ for some $t \in [0,1]$.

The first statement implies that $\theta(\psi)$ is a rational, while the second statement implies that $t = \theta$ for some $\psi$ (if we restrict ourselves to the same branch of the $\log$ function). So, $t$ is also a rational.

The Jupyter notebook walks through a complete construction of the solution to this problem. First, building up the QPE algorithm and constructing the oracle, $U_f$, to be used in Grover's algorithm. The primary function used is Grover_k(d,n,thetas,k), which will run Grover's algorithm for the above problem $k$ times for selected $d$ and $n$ and a given list of $\theta$ values. The target that Grover's algorithm searches for $t$ can be set globally.
