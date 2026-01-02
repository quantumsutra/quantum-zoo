Here is a possible outline for your book on quantum algorithms, based on the list from the Quantum Algorithm Zoo:

### **Book Title: A Comprehensive Guide to Quantum Algorithms**

---

### **Part 1: Foundations of Quantum Computation**

* **Chapter 1: Introduction to Quantum Mechanics**
    * Qubits, Superposition, and Entanglement
    * Quantum Gates and Circuits
    * Measurement
* **Chapter 2: The Quantum Fourier Transform**
    * Properties and Applications
    * Circuit Implementation

---

### **Part 2: Algebraic and Number Theoretic Algorithms**

* **Chapter 3: Shor's Algorithm and its Applications**
    * **Factoring**
    * **Discrete-log**
* **Chapter 4: Solving Problems in Algebraic Number Theory**
    * **Pell's Equation**
    * **Principal Ideal Problem**
    * **Unit Group and Class Group**
* **Chapter 5: Advanced Number Theoretic Problems**
    * **Gauss Sums**
    * **Primality Proving**
    * **Solving Exponential Congruences**

---

### **Part 3: Quantum Search and Optimization**

* **Chapter 6: Grover's Algorithm and its Variants**
    * Unstructured Search
    * Amplitude Amplification
* **Chapter 7: Adiabatic and Optimization Algorithms**
    * **Adiabatic Algorithms**
    * **Quantum Approximate Optimization Algorithm (QAOA)**

---

### **Part 4: Quantum Linear Algebra and Cryptanalysis**

* **Chapter 8: Quantum Approaches to Linear Algebra**
    * **Verifying Matrix Products**
    * **Matrix Rank**
* **Chapter 9: Quantum Cryptanalysis**
    * Breaking Classical Cryptosystems
    * **Quantum Cryptanalysis** of Symmetric and Asymmetric Ciphers
* **Chapter 10: Hidden Subgroup and Related Problems**
    * **Hidden Shift**
    * **Subset-sum**

---

### **Part 5: Specialized Quantum Algorithms**

* **Chapter 11: Algorithms for Group Theory and Representation Theory**
    * **Matrix Elements and Multiplicity Coefficients of Group Representations**
* **Chapter 12: Applications in Coding and Information Theory**
    * **Decoding**
* **Chapter 13: Miscellaneous and Puzzle-like Problems**
    * **Counterfeit Coins**

---

### **Appendices**

* **Appendix A: Mathematical Preliminaries**
    * Linear Algebra, Group Theory, Number Theory
* **Appendix B: Glossary of Quantum Computing Terms**

Of course. Here is an extensive table cataloging the quantum algorithms from the provided text, organized by category.

***

## Algebraic and Number Theoretic Algorithms

This class of algorithms leverages quantum properties, particularly the Quantum Fourier Transform, to solve problems in algebra and number theory, many of which are foundational to modern cryptography.

| Algorithm Name | Speedup | Description | Complexities (Quantum vs. Classical) | Implementations |
| :--- | :--- | :--- | :--- | :--- |
| **Factoring** | Superpolynomial | Finds the prime factorization of an n-bit integer. Breaks RSA public-key encryption. | **Q:** $O((\log N)^2 (\log \log N)(\log \log \log N))$ vs. **C:** $exp(O((\log N)^{1/3} (\log \log N)^{2/3}))$ | Classiq, Cirq, PennyLane, Qrisp |
| **Discrete-log** | Superpolynomial | Given $a, b, N$ where $b = a^s \pmod{N}$, finds $s$. Breaks Diffie-Hellman and elliptic curve crypto. | **Q:** $poly(n)$ vs. **C:** Superpolynomial in $n$. | Classiq, Qrisp |
| **Pell's Equation** | Superpolynomial | Finds the fundamental solution to the equation $x^2 - dy^2 = 1$ for a nonsquare integer $d$. | **Q:** $poly(n)$ vs. **C:** Not known to be polynomial. | - |
| **Principal Ideal** | Superpolynomial | Determines if an ideal in a quadratic number field is principal and finds its generator. | **Q:** $poly(n)$ vs. **C:** Not known to be polynomial. | - |
| **Unit Group** | Superpolynomial | Finds a set of generators for the group of units in the ring of integers of a number field. | **Q:** $poly(n)$ vs. **C:** Not known to be polynomial. | - |
| **Class Group** | Superpolynomial | Finds a set of generators for the class group of the ring of integers of a number field. | **Q:** $poly(\log(|\Delta|))$ vs. **C:** Not known to be polynomial. | - |
| **Gauss Sums** | Superpolynomial | Estimates Gauss sums over finite fields and rings to polynomial precision. | **Q:** $poly(n)$ vs. **C:** Not known to be polynomial. | - |
| **Primality Proving** | Polynomial | Returns a proof that a given n-bit number is prime. | **Q:** $\tilde{O}(n^3)$ vs. **C:** $\tilde{O}(n^4)$ | - |
| **Solving Exp. Congruences** | Polynomial | Finds integers $x_1, \dots, x_k$ for a given congruence of the form $a_1^{x_1} \dots a_k^{x_k} \equiv b \pmod{N}$. | **Q:** $L_N(1/3, c)$ vs. **C:** $L_N(1/2, c)$ | - |
| **Verifying Matrix Products** | Polynomial | Decides whether $AB=C$ for three $n \times n$ matrices. | **Q:** $O(n^{5/3})$ vs. **C:** $O(n^2)$ | - |
| **Subset-sum** | Polynomial | Determines if any subset of a list of integers sums to a target value $s$. | **Q:** $O(2^{0.241n})$ vs. **C:** $O(2^{0.291n})$ | - |

***




## Oracular Algorithms

These algorithms assume access to a "black box" or "oracle" that computes a function. The goal is to determine a property of the function using the minimum number of oracle queries, where quantum algorithms can offer significant speedups.

| Algorithm Name | Speedup | Description | Complexities (Quantum vs. Classical Queries) | Implementations |
| :--- | :--- | :--- | :--- | :--- |
| **Searching (Grover)** | Polynomial | Finds a "winning" input $w$ for an oracle function $f$ where $f(w)=1$. | **Q:** $O(\sqrt{N})$ vs. **C:** $O(N)$ | Classiq, Cirq, PennyLane, Qrisp |
| **Abelian Hidden Subgroup** | Superpolynomial | Finds a hidden subgroup $H$ of a finitely generated Abelian group $G$. | **Q:** $poly(\log|G|)$ vs. **C:** $exp(\log|G|)$ | Classiq, Cirq |
| **Non-Abelian Hidden Subgroup** | Superpolynomial | Finds a hidden subgroup $H$ of a non-Abelian group $G$. Solves graph isomorphism if solved for symmetric group. | **Q:** $poly(\log|G|)$ queries, but processing is generally exponential. | - |
| **Bernstein-Vazirani** | Polynomial | Finds a hidden n-bit string $h$ given an oracle that computes the bitwise inner product $x \cdot h$. | **Q:** $1$ query vs. **C:** $n$ queries | Classiq, Cirq, PennyLane |
| **Deutsch-Jozsa** | Exponential (vs. Deterministic) | Determines if a function is constant or balanced (half outputs 0, half 1). | **Q:** $1$ query vs. **C (Det.):** $2^{n-1}+1$ queries | Classiq, PennyLane |
| **Formula Evaluation** | Polynomial | Evaluates a Boolean formula where each variable is used once (a tree structure). | **Q:** $O(\sqrt{N})$ vs. **C:** $O(N^{0.753\dots})$ for NAND trees. | - |
| **Hidden Shift** | Superpolynomial | Given $f(x) = g(x+s)$ where $g$ is known, find the unknown shift $s$. | **Q:** $O(1)$ for some $g$ vs. **C:** Not known to be $poly(\log(N))$. | Classiq, Cirq |
| **Collision Finding** | Polynomial | For a two-to-one function $f$, find a pair $x, y$ such that $f(x)=f(y)$. | **Q:** $O(N^{1/3})$ vs. **C:** $O(\sqrt{N})$ | - |
| **Element Distinctness** | Polynomial | For a general function $f$, determine if there exist distinct inputs $x, y$ such that $f(x)=f(y)$. | **Q:** $O(N^{2/3})$ vs. **C:** $O(N)$ | - |
| **Welded Tree** | Superpolynomial | Finds a path from the entrance to the exit of a specific graph structure (welded binary trees). | **Q:** $poly(n)$ vs. **C:** Requires exponential queries. | Classiq |

***

## Approximation and Simulation Algorithms

These algorithms focus on simulating physical quantum systems or approximating mathematical quantities that are intractable for classical computers. Many of these problems are BQP-complete, meaning they are among the hardest problems efficiently solvable by a quantum computer.

| Algorithm Name | Speedup | Description | Details | Implementations |
| :--- | :--- | :--- | :--- | :--- |
| **Simulating Hamiltonian Dynamics** | Superpolynomial | Simulates the time evolution $e^{-iHt}$ of a quantum system described by a Hamiltonian $H$. | Foundational application of quantum computers. Assumed intractable classically for general local Hamiltonians. | Classiq, PennyLane, Qrisp |
| **Preparing Eigenstates/Thermal States** | Superpolynomial | Prepares ground states, low energy states, or thermal equilibrium states of Hamiltonians. | Crucial for quantum chemistry and materials science. Generally QMA-hard in the worst case. | - |
| **Knot Invariants (Jones Polynomial)** | Superpolynomial | Approximates the Jones polynomial for the plat closure of a braid, a BQP-complete problem. | Connects quantum computation to topological quantum field theory. | - |
| **Three-manifold Invariants** | Superpolynomial | Approximates topological invariants of 3D manifolds, such as the Turaev-Viro invariant. | BQP-complete for a given Heegaard splitting. | - |
| **Partition Functions** | Superpolynomial | Approximates the partition function for classical statistical mechanical systems like the Potts model. | Includes approximating the Tutte polynomial, which is BQP-complete for some parameters. | - |
| **Simulated Annealing** | Polynomial | Speeds up classical simulated annealing, a heuristic optimization method based on Markov chains. | Runtime scales as $O(1/\sqrt{\delta})$ vs. classical $O(1/\delta)$, where $\delta$ is the spectral gap. | - |

***

## Optimization, Numerics, and Machine Learning

This rapidly developing area applies quantum algorithms to enhance optimization, numerical analysis, and machine learning tasks, offering speedups that range from polynomial to exponential depending on the problem structure.

| Algorithm Name | Speedup | Description | Details | Implementations |
| :--- | :--- | :--- | :--- | :--- |
| **Adiabatic Algorithms** | Varies (Potentially Superpolynomial) | Solves optimization problems by slowly evolving the ground state of an easy-to-prepare Hamiltonian to a final Hamiltonian whose ground state encodes the solution. | Also known as Quantum Annealing. Power relative to classical computation is an active area of research. | Classiq (Linear Solver) |
| **Quantum Approx. Optimization (QAOA)** | Varies | A hybrid quantum-classical algorithm for finding approximate solutions to combinatorial optimization problems. | Potential for quantum advantage in the gap between what's efficiently solvable classically and what is NP-hard to approximate. | Classiq, Cirq, PennyLane, Qrisp |
| **Linear Systems (HHL)** | Superpolynomial | Solves a system of linear equations $Ax=b$ by preparing a quantum state $|x\rangle$ proportional to the solution vector. | Requires a sparse, well-conditioned matrix $A$. The solution is encoded in amplitudes, not a classical vector. | Classiq, Cirq, Qrisp/PennyLane |
| **Semidefinite Programming** | Polynomial | Finds the optimal solution for a semidefinite program, a type of convex optimization problem. | Achieves quadratic speedup when the rank $r$ of the solution is small compared to its dimension $n$. | - |
| **Machine Learning** | Varies | A broad category of algorithms applying quantum techniques (e.g., HHL, Grover) to speed up tasks like classification, clustering, and regression. | Speedups are often contingent on specific data access models (e.g., QRAM). Some have been "dequantized." | Classiq, PennyLane |
| **Solving Differential Equations** | Superpolynomial | Solves systems of linear or nonlinear ordinary/partial differential equations, with the solution encoded in a quantum state's amplitudes. | Speedup is typically exponential in dimension but polynomial in time and precision. | Classiq |

Of course! Here is the categorized list of quantum algorithms.

***

### ⚛️ Algebraic and Number Theoretic Algorithms
1.  Factoring
2.  Discrete-log
3.  Pell's Equation
4.  Principal Ideal
5.  Unit Group
6.  Class Group
7.  Gauss Sums
8.  Primality Proving
9.  Solving Exponential Congruences
10. Matrix Elements and Multiplicity Coefficients of Group Representations
11. Verifying Matrix Products
12. Subset-sum
13. Decoding
14. Quantum Cryptanalysis

***

### 🔮 Oracular Algorithms
15. Searching
16. Abelian Hidden Subgroup
17. Non-Abelian Hidden Subgroup
18. Bernstein-Vazirani
19. Deutsch-Jozsa
20. Formula Evaluation
21. Hidden Shift
22. Polynomial interpolation
23. Pattern matching
24. Ordered Search
25. Graph Properties in the Adjacency Matrix Model
26. Graph Properties in the Adjacency List Model
27. Welded Tree
28. Collision Finding and Element Distinctness
29. Graph Collision
30. Matrix Commutativity
31. Group Commutativity
32. Hidden Nonlinear Structures
33. Center of Radial Function
34. Group Order and Membership
35. Group Isomorphism
36. Statistical Difference
37. Finite Rings and Ideals
38. Counterfeit Coins
39. Matrix Rank
40. Matrix Multiplication over Semirings
41. Subset finding
42. Search with Wildcards
43. Network flows
44. Electrical Resistance
45. Junta Testing and Group Testing

***

### 🔬 Approximation and Simulation Algorithms
46. Simulating Quantum Hamiltonian Dynamics
47. Preparing Eigenstates and Thermal States
48. Knot Invariants
49. Three-manifold Invariants
50. Partition Functions
51. Zeta Functions
52. Weight Enumerators
53. Simulated Annealing
54. String Rewriting
55. Matrix Powers
56. Probabilistic Sampling

***

### 🧠 Optimization, Numerics, and Machine Learning
57. Polynomial Quantum Speedups for Constraint Satisfaction Problems
58. Adiabatic Algorithms
59. Quantum Approximate Optimization
60. Gradient Estimation and Learning Polynomials
61. Semidefinite Programming
62. Convex Optimization
63. Optimization by Decoded Quantum Interferometry
64. Linear Systems
65. Estimating Determinants and Other Spectral Sums
66. Machine Learning
67. Tensor Principal Component Analysis
68. Solving Linear Differential Equations
69. Solving Nonlinear Differential Equations
70. Quantum Dynamic Programming for path-in-the-hypercube
71. Computing the Principal Eigenvector
72. Approximating Nash Equilibria
73. Lattice Problems by Filtering
74. Double-bracket quantum algorithms
75. 

Of course. Here is an extensive chronological list of the quantum algorithms we've discussed, organized by the era in which their core ideas were first published. This timeline traces the intellectual development of the field, from foundational concepts to the cutting-edge of modern research.

---

### **The Dawn (The 1980s): The Founding Vision** visionary

This era is defined by the foundational idea that quantum mechanics could be used for computation.

* **1. Simulating Quantum Hamiltonian Dynamics (1982)**: The entire field began with a visionary talk by Richard Feynman. He observed that classical computers struggled to simulate quantum systems due to exponential overhead. He proposed building a computer that operated on quantum principles itself to naturally and efficiently simulate other quantum systems. This remains one of the most important and promising applications of quantum computing.
* **2. The Deutsch-Jozsa Algorithm (1985-1992)**: David Deutsch formalized the idea of a quantum computer and, in 1985, provided the first concrete example of a problem a quantum computer could solve faster than a classical deterministic one (for a single bit). The multi-bit generalization with Richard Jozsa in 1992 became a canonical "proof of concept" for quantum speedup.

---

### **The Revolution (Mid-1990s): The "Big Two" and the HSP Framework** 💥

This period saw the discovery of the two most famous quantum algorithms, which ignited the field and established the two major paradigms for quantum speedups: the Quantum Fourier Transform and Amplitude Amplification.

* **3. The Abelian Hidden Subgroup Problem (HSP) Framework (c. 1994-1995)**: Following the breakthrough of Shor's algorithm, researchers realized that a wide array of problems could be unified under this single algebraic framework. The standard quantum method for the HSP (prepare-query-QFT-measure) is the engine behind all of the following:
    * **Factoring (Shor's Algorithm, 1994)**: The "killer app." Showed a quantum computer could break RSA encryption.
    * **Discrete Logarithm (Shor's Algorithm, 1994)**: Published in the same paper, it breaks Diffie-Hellman and elliptic curve cryptography.
    * **Bernstein-Vazirani Algorithm (1993)**: A simple but perfect illustration of extracting a global property (a hidden string) with one query, using the "Hadamard sandwich" which is a form of the QFT.
    * **Group Order, Membership, and Isomorphism (c. 1995-2000s)**: It was soon realized that the HSP toolkit could be used to efficiently "reverse-engineer" the structure of black-box Abelian groups.
    * **Finite Rings and Ideals (c. 2001)**: The HSP framework was further extended to analyze the additive structure of rings, allowing a whole suite of problems in this more complex algebraic setting to be solved.
* **4. Searching (Grover's Algorithm, 1996)**: The second major algorithm, providing a quadratic speedup for unstructured search. Its underlying technique, **Amplitude Amplification**, became a general-purpose tool for boosting success probabilities and accelerating search-like components of other algorithms.
* **5. Collision Finding (1998)**: One of the earliest applications of Grover's algorithm, the BHT algorithm provided a polynomial speedup for the collision problem, a key task in cryptanalysis.

---

### **The New Millennium (Early 2000s): New Models, New Problems, New Tools** 🚀

With the main paradigms established, the 2000s saw an explosion of creativity, with researchers generalizing the known techniques and discovering entirely new models and problem classes where quantum computers could excel.

* **6. Adiabatic Algorithms & Quantum Annealing (2000)**: Farhi et al. proposed an entirely new model of quantum computation based on the quantum adiabatic theorem, which solves problems by slowly morphing a simple system into one whose ground state encodes the solution. This is particularly natural for optimization problems.
* **7. Hallgren's Breakthrough - HSP on the Reals (2002)**: Sean Hallgren provided the next major theoretical leap after Shor by showing how to solve the Hidden Subgroup Problem for continuous groups. This opened the door to solving a new class of number-theoretic problems intractable for Shor's original method, including:
    * **Pell's Equation**
    * **Principal Ideal Problem**
    * **Finding the Unit Group and Class Group**
* **8. The Rise of Quantum Walks (c. 2001-2004)**: Quantum walks were developed as the quantum analogue of classical random walks. They proved to be a new, powerful tool for algorithm design.
    * **Welded Tree Problem (2003)**: A stunning demonstration of an exponential speedup for a graph traversal problem that is not an instance of the HSP.
    * **Element Distinctness (2004)**: Ambainis's landmark algorithm for collision finding, which became the core primitive for many other speedups.
    * **Quantum-Enhanced Simulated Annealing (2004)**: Szegedy showed how any classical Markov chain could be "quantized" to achieve a quadratic speedup, directly applicable to the simulated annealing heuristic.
    * **Graph Problems (c. 2004-2007)**: Quantum walks and advanced search were applied to a wide range of graph problems, leading to polynomial speedups for Connectivity, MST, Triangle Finding, Graph Collision, and more.
* **9. New BQP-Complete Problems (c. 1998-2007)**: Researchers found that the essence of quantum computational power (the class BQP) could be captured by a surprising variety of problems from different fields.
    * **Weight Enumerators (1998)**: A problem from classical coding theory involving sums of complex phases.
    * **Knot Invariants & Three-manifold Invariants (c. 2003-2005)**: The profound discovery that approximating the Jones polynomial and other topological invariants is equivalent in difficulty to running a quantum computer.
    * **Partition Functions, String Rewriting, & Matrix Powers (c. 2005-2007)**: Further work showed this "sum over interfering paths" structure appears in problems from physics and theoretical computer science, all of which are BQP-complete.
* **10. New Numerical and Algebraic Primitives (c. 2005-2006)**:
    * **Gradient Estimation (2005)**: A key primitive for quantum optimization and machine learning, showing how to calculate a multi-dimensional derivative in a single query.
    * **Computing Zeta Functions of Curves (2006)**: A specialized quantum speedup for a deep problem in number theory with applications to cryptography.

---

### **The Modern Era (Late 2000s - Present): The QML Revolution and Beyond** 🤖

The discovery of the HHL algorithm in 2009 kicked off a new era focused on data, machine learning, and finding practical applications for near-term hardware.

* **11. The HHL Revolution (2009)**: The algorithm for solving systems of linear equations by Harrow, Hassidim, and Lloyd sparked the field of Quantum Machine Learning. It provides an exponential speedup under specific conditions and serves as the foundation for algorithms that solve:
    * **Linear Differential Equations**
    * **Electrical Resistance**
    * **Principal Component Analysis** and many other QML tasks.
* **12. The Rise of Hybrid Algorithms and QML (c. 2014-Present)**: As the challenges of building fault-tolerant quantum computers became clear, focus shifted to algorithms for near-term (NISQ) devices.
    * **Quantum Approximate Optimization Algorithm (QAOA) (2014)**: A hybrid algorithm inspired by the adiabatic model, designed to find approximate solutions to optimization problems on gate-based hardware.
    * **Variational Algorithms (for Preparing Eigenstates, etc.)**: This general class of hybrid algorithms, including VQE, became a dominant paradigm for near-term research in quantum chemistry and machine learning.
    * **Quantum Machine Learning**: The broader field exploded with new ideas, including quantum kernel methods, quantum neural networks, and a more nuanced understanding of where genuine quantum advantage might lie after some early algorithms were "dequantized."
* **13. Recent Breakthroughs (c. 2017-Present)**: Research continues to uncover novel quantum algorithmic paradigms.
    * **Optimization by Decoded Quantum Interferometry (DQI) (2017)**: A new hybrid model that transforms optimization problems into error-correction problems.
    * **Quantum Dynamic Programming (2019)**: A general method for achieving a quadratic speedup on a wide range of classical dynamic programming algorithms for NP-hard problems.
    * **Double-bracket quantum algorithms (c. 2021)**: A new approach to optimization and simulation based on continuous-time flows from differential geometry.
    * **Lattice Problems by Filtering (2022)**: A major new development in quantum cryptanalysis, providing the first exponential speedup for a class of lattice problems that underlie post-quantum cryptography.

Of course. Based on our extensive exploration of 73 different quantum algorithms, here is a comprehensive and updated outline for "The Big Book of Quantum Algorithms."

This structure organizes the algorithms thematically, telling the story of the field from its foundational principles to the cutting edge of research.

***

# **The Big Book of Quantum Algorithms**

---

## **Part I: Foundations of Quantum Computation** ⚛️

This part lays the groundwork, introducing the fundamental concepts and the core mathematical machinery that powers all quantum algorithms.

* **Chapter 1: The Quantum Revolution**
    * Why Quantum Computing? Feynman's Vision
    * The Landscape of Computational Complexity (P, NP, BQP)
    * The Power and Perils of a Quantum Future
* **Chapter 2: The Language of Quantum Mechanics**
    * Qubits: Beyond 0 and 1 
    * Superposition and Interference: The Heart of Quantum Power
    * Entanglement: "Spooky Action at a Distance"
    * The Mathematics of Hilbert Space
* **Chapter 3: The Circuit Model: A Blueprint for Computation**
    * Single-Qubit Gates: Rotations and Flips
    * Multi-Qubit Gates: The CNOT and Controlled Operations
    * Measurement: Collapsing the Wavefunction
    * Universal Gate Sets
* **Chapter 4: The Algorithmic Primitives: Core Quantum Engines**
    * **The Quantum Fourier Transform (QFT)**: The master key for periodicity and phase.
    * **Amplitude Amplification & Quantum Counting**: The engine of quantum search.
    * **Phase Kickback**: Turning an oracle's answer into a phase.

---

## **Part II: The Oracle Model and Fundamental Speedups** 🔮

This part explores the first simple, yet profound, algorithms that proved a quantum computer could be superior, primarily by using a "black box" or oracle more efficiently.

* **Chapter 5: Probing the Black Box: Simple Oracle Problems**
    * The Deutsch-Jozsa Algorithm: The First Separation
    * The Bernstein-Vazirani Algorithm: Learning a Secret in One Shot
* **Chapter 6: The Grover Revolution: The Power of Quantum Search**
    * Searching Unstructured Data: Grover's Algorithm
    * Applications: Quadratic Speedups for Constraint Satisfaction Problems (CSPs)
* **Chapter 7: The Power of Quantum Walks: Beyond Simple Search**
    * From Random Walks to Quantum Leaps
    * Element Distinctness and Collision Finding
    * Applications: Graph Collision, Group Commutativity, and Subset Finding

---

## **Part III: The Power of the Fourier Transform: Algebraic Problems** 🔢

This part dives into the algorithms that deliver exponential speedups, almost all of which are built on the QFT and the general framework of the Hidden Subgroup Problem (HSP).

* **Chapter 8: The Hidden Subgroup Problem: A Unifying Framework**
    * The Abelian HSP: The Standard Method for Quantum Supremacy
    * The Non-Abelian HSP: The Holy Grail of Quantum Algorithms
* **Chapter 9: Shor's Algorithm: Breaking Modern Cryptography**
    * Integer Factoring
    * The Discrete Logarithm Problem
* **Chapter 10: Beyond Shor: HSP in Algebraic Number Theory**
    * Pell's Equation
    * The Principal Ideal Problem
    * Finding the Unit Group and Class Group
* **Chapter 11: Reverse-Engineering Black-Box Groups**
    * Finding Group Order and Membership
    * The Group Isomorphism Problem
* **Chapter 12: Other Fourier-Based Algebraic Algorithms**
    * The Hidden Shift Problem
    * Estimating Gauss Sums
    * Polynomial Interpolation and Reconstruction
    * Solving Exponential Congruences

---

## **Part IV: Quantum Simulation: The Original Motivation** 🔬

This part returns to Feynman's original vision, exploring how quantum computers can simulate the natural world at its most fundamental level.

* **Chapter 13: Simulating Hamiltonian Dynamics**
    * The Schrödinger Equation and the Problem of Simulation
    * Trotterization: The First Step
    * Advanced Methods: Qubitization and Quantum Signal Processing
* **Chapter 14: Finding Ground States and Thermal States**
    * The Importance of Eigenstates and Equilibrium
    * Methods: Quantum Phase Estimation (QPE), Adiabatic State Preparation, and VQE
    * Preparing Thermal States: Quantum Gibbs Sampling
* **Chapter 15: The Nature of Quantum Hardness: BQP-Complete Problems**
    * The Deep Connection: Simulating Topological Quantum Field Theories (TQFTs)
    * Knot Invariants (The Jones Polynomial)
    * Three-Manifold Invariants (Turaev-Viro)
    * The Deep Connection: Sums Over Paths and Histories
    * Partition Functions
    * String Rewriting
    * Approximating Matrix Powers
    * Quadratically Signed Weight Enumerators

---

## **Part V: Quantum Algorithms for Data, Optimization, and ML** 🧠

This part covers the modern era of algorithm development, focusing on practical applications in numerical analysis, large-scale optimization, and the booming field of machine learning.

* **Chapter 16: Quantum Linear Algebra**
    * The HHL Algorithm: Solving Systems of Linear Equations
    * Applications: Solving Linear and Nonlinear Differential Equations
    * Estimating Determinants and Other Spectral Sums
    * Finding the Principal Eigenvector (Principal Component Analysis)
    * Matrix Rank and Commutativity
* **Chapter 17: A Tour of Quantum Optimization**
    * Adiabatic Algorithms and Quantum Annealing
    * The Quantum Approximate Optimization Algorithm (QAOA)
    * Quantum Dynamic Programming: Speeding up NP-Hard Problems
    * Optimization by Decoded Quantum Interferometry (DQI)
* **Chapter 18: Convex Optimization and Game Theory**
    * General Convex Optimization
    * Semidefinite and Linear Programming
    * Approximating Nash Equilibria
* **Chapter 19: Quantum Machine Learning: A Guided Tour**
    * HHL-based QML and the "Dequantization" Problem
    * Grover-based QML: Quadratic Speedups
    * Variational Circuits: Quantum Kernels and Neural Networks
    * Specialized Algorithms: Tensor PCA, Junta Testing

---

## **Part VI: Frontiers and Specialized Algorithms** 🗺️

This final part explores advanced, specialized, and cutting-edge algorithms that push the boundaries of what we know about quantum computation.

* **Chapter 20: Advanced Algorithms for Graphs and Structures**
    * The Welded Tree Problem: An Exponential Speedup from Quantum Walks
    * Graph Properties in the Adjacency Matrix and List Models
    * Network Flows and Electrical Resistance
* **Chapter 21: Puzzles, Games, and Niche Problems**
    * The Counterfeit Coin Problem
    * Ordered Search
    * Search with Wildcards
    * Decoding Classical Error-Correcting Codes
* **Chapter 22: The Cutting Edge: New Frontiers**
    * Lattice Problems by Filtering: A New Attack on Post-Quantum Crypto
    * Double-Bracket Quantum Algorithms: A New Paradigm from Geometry

---

### **Appendices**

* **Appendix A: Mathematical Preliminaries**
    * Linear Algebra, Group Theory, Number Theory, and Complexity Theory
* **Appendix B: Glossary of Quantum Computing Terms**

# Tree


```python
import plotly.graph_objects as go

# Define the hierarchical structure of the book content
# Each item has a unique ID, a display label, and a parent ID.
# The root's parent is an empty string "".

ids = [
    # Root
    "root",

    # --- Part I: Foundations ---
    "part-i", "chapter-1", "chapter-2", "chapter-3", "chapter-4",
    "topic-feynman", "topic-complexity", "topic-qubits", "topic-gates",
    "topic-primitives-qft", "topic-primitives-aa", "topic-primitives-pk",

    # --- Part II: Oracles & Search ---
    "part-ii", "chapter-5", "chapter-6", "chapter-7",
    "algo-dj", "algo-bv", "algo-grover", "algo-csp-grover",
    "topic-qwalks", "algo-ed-collision", "algo-graph-collision",
    "algo-group-commutativity", "algo-subset-finding",

    # --- Part III: Fourier Transform & Algebra ---
    "part-iii", "chapter-8", "chapter-9", "chapter-10", "chapter-11", "chapter-12",
    "topic-hsp-abelian", "topic-hsp-nonabelian", "algo-factoring", "algo-discrete-log",
    "algo-pells", "algo-principal-ideal", "algo-unit-group", "algo-class-group",
    "algo-group-order", "algo-group-iso", "algo-hidden-shift", "algo-gauss-sums",
    "algo-poly-interp", "algo-exp-congruences",

    # --- Part IV: Simulation ---
    "part-iv", "chapter-13", "chapter-14", "chapter-15",
    "algo-ham-sim", "topic-trotter", "topic-qsp", "algo-eigenstates",
    "topic-qpe-vqe", "algo-thermal-states", "topic-bqp-complete", "algo-knots",
    "algo-3-manifolds", "algo-partition-funcs", "algo-string-rewriting",
    "algo-matrix-powers", "algo-weight-enumerators",

    # --- Part V: Data, Opto, & ML ---
    "part-v", "chapter-16", "chapter-17", "chapter-18", "chapter-19",
    "algo-hhl", "algo-diff-eq", "algo-determinants", "algo-pca", "algo-matrix-rank-comm",
    "algo-adiabatic", "algo-qaoa", "algo-qdp", "algo-dqi", "algo-convex-opto",
    "algo-sdp-lp", "algo-nash", "topic-qml-hhl", "topic-qml-grover",
"topic-qml-variational", "topic-qml-specialized",

    # --- Part VI: Frontiers ---
    "part-vi", "chapter-20", "chapter-21", "chapter-22",
    "algo-welded-tree", "algo-graph-props", "algo-network-flows-resistance",
    "algo-counterfeit-coin", "algo-ordered-search", "algo-wildcards", "algo-decoding",
    "algo-lattice-filtering", "algo-double-bracket"
]

labels = [
    # Root
    "<b>The Big Book of Quantum Algorithms</b>",

    # --- Part I: Foundations ---
    "<b>Part I: Foundations</b>", "Chapter 1: The Quantum Revolution", "Chapter 2: Language of QM", "Chapter 3: The Circuit Model", "Chapter 4: Algorithmic Primitives",
    "Feynman's Vision", "Complexity Classes", "Qubits & Entanglement", "Gates & Circuits",
    "Quantum Fourier Transform (QFT)", "Amplitude Amplification", "Phase Kickback",

    # --- Part II: Oracles & Search ---
    "<b>Part II: Oracles & Search</b>", "Chapter 5: Simple Oracle Problems", "Chapter 6: The Grover Revolution", "Chapter 7: The Power of Quantum Walks",
    "Deutsch-Jozsa", "Bernstein-Vazirani", "Grover's Search", "CSP Speedups",
    "Quantum Walk Intro", "Element Distinctness", "Graph Collision",
    "Group Commutativity", "Subset Finding",

    # --- Part III: Fourier Transform & Algebra ---
    "<b>Part III: Algebra (QFT)</b>", "Chapter 8: The HSP Framework", "Chapter 9: Shor's Algorithm", "Chapter 10: Algebraic Number Theory", "Chapter 11: Black-Box Groups", "Chapter 12: Other Fourier Algorithms",
    "Abelian HSP", "Non-Abelian HSP", "Factoring", "Discrete Logarithm",
    "Pell's Equation", "Principal Ideal", "Unit Group", "Class Group",
    "Group Order/Membership", "Group Isomorphism", "Hidden Shift", "Gauss Sums",
    "Polynomial Interpolation", "Exponential Congruences",

    # --- Part IV: Simulation ---
    "<b>Part IV: Quantum Simulation</b>", "Chapter 13: Hamiltonian Dynamics", "Chapter 14: Eigenstates & Thermal States", "Chapter 15: BQP-Complete Problems",
    "Hamiltonian Simulation", "Trotterization", "Qubitization/QSP", "Preparing Eigenstates",
    "QPE & VQE", "Preparing Thermal States", "Nature of BQP-Hardness", "Knot Invariants",
    "3-Manifold Invariants", "Partition Functions", "String Rewriting",
    "Matrix Powers", "Weight Enumerators",

    # --- Part V: Data, Opto, & ML ---
    "<b>Part V: Data, Opto, & ML</b>", "Chapter 16: Quantum Linear Algebra", "Chapter 17: Quantum Optimization", "Chapter 18: Convex Opto & Games", "Chapter 19: Quantum Machine Learning",
    "HHL (Linear Systems)", "Solving Differential Eqs", "Estimating Determinants", "Principal Eigenvector (PCA)", "Matrix Rank/Commutativity",
    "Adiabatic Algorithms", "QAOA", "Quantum Dynamic Programming", "DQI", "Convex Optimization",
    "Semidefinite/Linear Programming", "Approximating Nash Equilibria", "HHL-based QML", "Grover-based QML",
    "Variational QML (Kernels)", "Specialized QML (Tensor PCA)",

    # --- Part VI: Frontiers ---
    "<b>Part VI: Frontiers</b>", "Chapter 20: Advanced Graph Algorithms", "Chapter 21: Puzzles & Niche Problems", "Chapter 22: The Cutting Edge",
    "Welded Tree", "Graph Properties", "Network Flows & Resistance",
    "Counterfeit Coin", "Ordered Search", "Search with Wildcards", "Decoding",
    "Lattice Problems by Filtering", "Double-Bracket Algorithms"
]

parents = [
    # Root
    "",

    # --- Part I: Foundations ---
    "root", "part-i", "part-i", "part-i", "part-i",
    "chapter-1", "chapter-1", "chapter-2", "chapter-3",
    "chapter-4", "chapter-4", "chapter-4",

    # --- Part II: Oracles & Search ---
    "root", "part-ii", "part-ii", "part-ii",
    "chapter-5", "chapter-5", "chapter-6", "chapter-6",
    "chapter-7", "chapter-7", "chapter-7", "chapter-7", "chapter-7",

    # --- Part III: Fourier Transform & Algebra ---
    "root", "part-iii", "part-iii", "part-iii", "part-iii", "part-iii",
    "chapter-8", "chapter-8", "chapter-9", "chapter-9",
    "chapter-10", "chapter-10", "chapter-10", "chapter-10",
    "chapter-11", "chapter-11", "chapter-12", "chapter-12", "chapter-12", "chapter-12",

    # --- Part IV: Simulation ---
    "root", "part-iv", "part-iv", "part-iv",
    "chapter-13", "chapter-13", "chapter-13", "chapter-14",
    "chapter-14", "chapter-14", "chapter-15", "chapter-15", "chapter-15", "chapter-15",
    "chapter-15", "chapter-15", "chapter-15",

    # --- Part V: Data, Opto, & ML ---
    "root", "part-v", "part-v", "part-v", "part-v",
    "chapter-16", "chapter-16", "chapter-16", "chapter-16", "chapter-16",
    "chapter-17", "chapter-17", "chapter-17", "chapter-17", "chapter-18",
    "chapter-18", "chapter-18", "chapter-19", "chapter-19", "chapter-19", "chapter-19",

    # --- Part VI: Frontiers ---
    "root", "part-vi", "part-vi", "part-vi",
    "chapter-20", "chapter-20", "chapter-20",
    "chapter-21", "chapter-21", "chapter-21", "chapter-21",
    "chapter-22", "chapter-22"
]

# Create the figure
fig = go.Figure(go.Treemap(
    ids=ids,
    labels=labels,
    parents=parents,
    root_color="lightgrey"
))

# Update layout for a better view
fig.update_layout(
    title_text="Hierarchical Outline: The Big Book of Quantum Algorithms",
    title_x=0.5,
    margin=dict(t=50, l=25, r=25, b=25)
)

# Show the interactive plot
fig.show()
```




```python
import plotly.graph_objects as go
import pandas as pd

# Original data from your prompt
data = {
    "Algorithm": [
        "1. Factoring", "2. Discrete-log", "3. Pell's Equation", "4. Principal Ideal",
        "5. Unit Group", "6. Class Group", "7. Gauss Sums", "8. Primality Proving",
        "9. Solving Exponential Congruences", "10. Matrix Elements...", "11. Verifying Matrix Products",
        "12. Subset-sum", "13. Decoding", "14. Quantum Cryptanalysis",
        "15. Searching", "16. Abelian Hidden Subgroup", "17. Non-Abelian Hidden Subgroup",
        "18. Bernstein-Vazirani", "19. Deutsch-Jozsa", "20. Formula Evaluation", "21. Hidden Shift",
        "22. Polynomial interpolation", "23. Pattern matching", "24. Ordered Search",
        "25. Graph Properties (Matrix Model)", "26. Graph Properties (List Model)", "27. Welded Tree",
        "28. Collision Finding & ED", "29. Graph Collision", "30. Matrix Commutativity",
        "31. Group Commutativity", "32. Hidden Nonlinear Structures", "33. Center of Radial Function",
        "34. Group Order & Membership", "35. Group Isomorphism", "36. Statistical Difference",
        "37. Finite Rings and Ideals", "38. Counterfeit Coins", "39. Matrix Rank",
        "40. Matrix Multiplication (Semirings)", "41. Subset finding", "42. Search with Wildcards",
        "43. Network flows", "44. Electrical Resistance", "45. Junta Testing & Group Testing",
        "46. Simulating Hamiltonian Dynamics", "47. Preparing Eigenstates & Thermal States",
        "48. Knot Invariants", "49. Three-manifold Invariants", "50. Partition Functions",
        "51. Zeta Functions", "52. Weight Enumerators", "53. Simulated Annealing",
        "54. String Rewriting", "55. Matrix Powers", "56. Probabilistic Sampling",
        "57. CSPs Speedups", "58. Adiabatic Algorithms", "59. Quantum Approximate Optimization",
        "60. Gradient Estimation", "61. Semidefinite Programming", "62. Convex Optimization",
        "63. Optimization by DQI", "64. Linear Systems", "65. Estimating Determinants",
        "66. Machine Learning", "67. Tensor PCA", "68. Solving Linear DEs",
        "69. Solving Nonlinear DEs", "70. Quantum Dynamic Programming", "71. Computing Principal Eigenvector",
        "72. Approximating Nash Equilibria", "73. Lattice Problems by Filtering", "74. Double-bracket algorithms"
    ],
    "Category": [
        "⚛️ Algebraic & Number Theoretic", "⚛️ Algebraic & Number Theoretic", "⚛️ Algebraic & Number Theoretic", "⚛️ Algebraic & Number Theoretic",
        "⚛️ Algebraic & Number Theoretic", "⚛️ Algebraic & Number Theoretic", "⚛️ Algebraic & Number Theoretic", "⚛️ Algebraic & Number Theoretic",
        "⚛️ Algebraic & Number Theoretic", "⚛️ Algebraic & Number Theoretic", "⚛️ Algebraic & Number Theoretic",
        "⚛️ Algebraic & Number Theoretic", "⚛️ Algebraic & Number Theoretic", "⚛️ Algebraic & Number Theoretic",
        "🔮 Oracular", "🔮 Oracular", "🔮 Oracular", "🔮 Oracular", "🔮 Oracular",
        "🔮 Oracular", "🔮 Oracular", "🔮 Oracular", "🔮 Oracular", "🔮 Oracular",
        "🔮 Oracular", "🔮 Oracular", "🔮 Oracular", "🔮 Oracular", "🔮 Oracular",
        "🔮 Oracular", "🔮 Oracular", "🔮 Oracular", "🔮 Oracular", "🔮 Oracular",
        "🔮 Oracular", "🔮 Oracular", "🔮 Oracular", "🔮 Oracular", "🔮 Oracular",
        "🔮 Oracular", "🔮 Oracular", "🔮 Oracular", "🔮 Oracular", "🔮 Oracular",
        "🔮 Oracular",
        "🔬 Approximation & Simulation", "🔬 Approximation & Simulation", "🔬 Approximation & Simulation",
        "🔬 Approximation & Simulation", "🔬 Approximation & Simulation", "🔬 Approximation & Simulation",
        "🔬 Approximation & Simulation", "🔬 Approximation & Simulation", "🔬 Approximation & Simulation",
        "🔬 Approximation & Simulation", "🔬 Approximation & Simulation",
        "🧠 Optimization, Numerics, & ML", "🧠 Optimization, Numerics, & ML", "🧠 Optimization, Numerics, & ML",
        "🧠 Optimization, Numerics, & ML", "🧠 Optimization, Numerics, & ML", "🧠 Optimization, Numerics, & ML",
        "🧠 Optimization, Numerics, & ML", "🧠 Optimization, Numerics, & ML", "🧠 Optimization, Numerics, & ML",
        "🧠 Optimization, Numerics, & ML", "🧠 Optimization, Numerics, & ML", "🧠 Optimization, Numerics, & ML",
        "🧠 Optimization, Numerics, & ML", "🧠 Optimization, Numerics, & ML", "🧠 Optimization, Numerics, & ML",
        "🧠 Optimization, Numerics, & ML", "🧠 Optimization, Numerics, & ML", "🧠 Optimization, Numerics, & ML"
    ]
}
df = pd.DataFrame(data)

# --- FIX STARTS HERE ---

# Define the root of the hierarchy
root_label = "Quantum Algorithms"

# Create lists to hold the full hierarchy for the plot
ids = [root_label]
labels = [root_label]
parents = [""] # The root has no parent

# Add the categories, with the root as their parent
unique_categories = df['Category'].unique()
for category in unique_categories:
    ids.append(category)
    labels.append(category)
    parents.append(root_label)

# Add the algorithms, with their respective category as their parent
ids.extend(df['Algorithm'])
labels.extend(df['Algorithm'])
parents.extend(df['Category'])

# --- FIX ENDS HERE ---


# Create the Sunburst figure using the corrected hierarchical lists
fig = go.Figure(go.Sunburst(
    ids=ids,
    labels=labels,
    parents=parents,
    hovertemplate='<b>%{label}</b><br>Parent: %{parent}<extra></extra>'
))

# Update the layout for a better visual
fig.update_layout(
    margin=dict(t=50, l=25, r=25, b=25),
    title_text="Hierarchical Tree of Quantum Algorithms",
    title_x=0.5,
)

# Show the interactive plot
fig.show()
```



# HTML

```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Quantum Algorithm Zoo - Tree Visualization</title>
    <style>
        .node circle {
            fill: #fff;
            stroke: steelblue;
            stroke-width: 1.5px;
        }
        .node {
            font: 12px sans-serif;
            font-weight: bold;
        }
        .link {
            fill: none;
            stroke: #ccc;
            stroke-width: 1.5px;
        }
    </style>
    <script src="https://d3js.org/d3.v3.min.js"></script>
</head>
<body>
    <script>
        var width = 1200,
            height = 3000;

        var cluster = d3.layout.cluster()
            .size([height, width - 400]);

        var diagonal = d3.svg.diagonal()
            .projection(function(d) { return [d.y, d.x]; });

        var svg = d3.select("body").append("svg")
            .attr("width", width)
            .attr("height", height)
            .append("g")
            .attr("transform", "translate(120,0)");

        var root = getData(),
            nodes = cluster.nodes(root),
            links = cluster.links(nodes);

        var link = svg.selectAll(".link")
            .data(links)
            .enter().append("path")
            .attr("class", "link")
            .attr("d", diagonal);

        var node = svg.selectAll(".node")
            .data(nodes)
            .enter().append("g")
            .attr("class", "node")
            .attr("transform", function(d) { return "translate(" + d.y + "," + d.x + ")"; });

        node.append("circle")
            .attr("r", 4.5);

        node.append("text")
            .attr("dx", function(d) { return d.children ? -10 : 10; })
            .attr("dy", 3)
            .style("text-anchor", function(d) { return d.children ? "end" : "start"; })
            .text(function(d) { return d.name; });

        function getData() {
            return {
                "name": "Quantum Algorithms",
                "children": [{
                        "name": "⚛️ Algebraic & Number Theoretic",
                        "children": [
                            {"name": "1. Factoring"},
                            {"name": "2. Discrete-log"},
                            {"name": "3. Pell's Equation"},
                            {"name": "4. Principal Ideal"},
                            {"name": "5. Unit Group"},
                            {"name": "6. Class Group"},
                            {"name": "7. Gauss Sums"},
                            {"name": "8. Primality Proving"},
                            {"name": "9. Solving Exponential Congruences"},
                            {"name": "10. Matrix Elements..."},
                            {"name": "11. Verifying Matrix Products"},
                            {"name": "12. Subset-sum"},
                            {"name": "13. Decoding"},
                            {"name": "14. Quantum Cryptanalysis"}
                        ]
                    },
                    {
                        "name": "🔮 Oracular Algorithms",
                        "children": [
                            {"name": "15. Searching"},
                            {"name": "16. Abelian Hidden Subgroup"},
                            {"name": "17. Non-Abelian Hidden Subgroup"},
                            {"name": "18. Bernstein-Vazirani"},
                            {"name": "19. Deutsch-Jozsa"},
                            {"name": "20. Formula Evaluation"},
                            {"name": "21. Hidden Shift"},
                            {"name": "22. Polynomial interpolation"},
                            {"name": "23. Pattern matching"},
                            {"name": "24. Ordered Search"},
                            {"name": "25. Graph Properties (Matrix Model)"},
                            {"name": "26. Graph Properties (List Model)"},
                            {"name": "27. Welded Tree"},
                            {"name": "28. Collision Finding & ED"},
                            {"name": "29. Graph Collision"},
                            {"name": "30. Matrix Commutativity"},
                            {"name": "31. Group Commutativity"},
                            {"name": "32. Hidden Nonlinear Structures"},
                            {"name": "33. Center of Radial Function"},
                            {"name": "34. Group Order & Membership"},
                            {"name": "35. Group Isomorphism"},
                            {"name": "36. Statistical Difference"},
                            {"name": "37. Finite Rings and Ideals"},
                            {"name": "38. Counterfeit Coins"},
                            {"name": "39. Matrix Rank"},
                            {"name": "40. Matrix Multiplication (Semirings)"},
                            {"name": "41. Subset finding"},
                            {"name": "42. Search with Wildcards"},
                            {"name": "43. Network flows"},
                            {"name": "44. Electrical Resistance"},
                            {"name": "45. Junta Testing & Group Testing"}
                        ]
                    },
                    {
                        "name": "🔬 Approximation & Simulation",
                        "children": [
                            {"name": "46. Simulating Hamiltonian Dynamics"},
                            {"name": "47. Preparing Eigenstates & Thermal States"},
                            {"name": "48. Knot Invariants"},
                            {"name": "49. Three-manifold Invariants"},
                            {"name": "50. Partition Functions"},
                            {"name": "51. Zeta Functions"},
                            {"name": "52. Weight Enumerators"},
                            {"name": "53. Simulated Annealing"},
                            {"name": "54. String Rewriting"},
                            {"name": "55. Matrix Powers"},
                            {"name": "56. Probabilistic Sampling"}
                        ]
                    },
                    {
                        "name": "🧠 Optimization, Numerics, & ML",
                        "children": [
                            {"name": "57. CSPs Speedups"},
                            {"name": "58. Adiabatic Algorithms"},
                            {"name": "59. Quantum Approximate Optimization"},
                            {"name": "60. Gradient Estimation"},
                            {"name": "61. Semidefinite Programming"},
                            {"name": "62. Convex Optimization"},
                            {"name": "63. Optimization by DQI"},
                            {"name": "64. Linear Systems"},
                            {"name": "65. Estimating Determinants"},
                            {"name": "66. Machine Learning"},
                            {"name": "67. Tensor PCA"},
                            {"name": "68. Solving Linear DEs"},
                            {"name": "69. Solving Nonlinear DEs"},
                            {"name": "70. Quantum Dynamic Programming"},
                            {"name": "71. Computing Principal Eigenvector"},
                            {"name": "72. Approximating Nash Equilibria"},
                            {"name": "73. Lattice Problems by Filtering"},
                            {"name": "74. Double-bracket algorithms"}
                        ]
                    }
                ]
            };
        }
    </script>
</body>
</html>
```


