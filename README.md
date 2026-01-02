# Quantum Algorithms: A Comprehensive Collection 🌌

A comprehensive repository documenting the entire landscape of quantum algorithms, from foundational concepts to cutting-edge applications. This collection organizes quantum algorithms into four major families, each leveraging quantum mechanical properties like superposition, entanglement, and interference to solve computational problems.

## 📚 Repository Structure

This repository is organized into two main components:

### 1. **Introduction & Overview** (Root Directory)
- **[1-Introduction.ipynb](1-Introduction.ipynb)** - Overview of the quantum computing paradigm and the four algorithm families
- **[1.1-Algebraic and Number.ipynb](1.1-Algebraic%20and%20Number.ipynb)** - Algebraic and Number Theoretic algorithms
- **[1.2-Oracular Algorithms.ipynb](1.2-Oracular%20Algorithms.ipynb)** - Black-box query algorithms
- **[1.3-Approximation and Simulation.ipynb](1.3-Approximation%20and%20Simulation.ipynb)** - Simulation and approximation techniques
- **[1.4-Optimization and Machine Learning.ipynb](1.4-Optimization%20and%20Machine%20Learning.ipynb)** - Optimization and ML applications

### 2. **AlgoZoo/** - Detailed Algorithm Implementations
An extensive catalog of 100+ quantum algorithms, each with detailed explanations, mathematical foundations, and implementations.

## 🧮 Algorithm Categories

### 1. Algebraic and Number Theoretic Algorithms
**Core Mechanism**: Hidden Subgroup Problem (HSP) and Quantum Fourier Transform (QFT)

Algorithms that exploit hidden mathematical structures to solve number theory problems exponentially faster than classical approaches.

**Featured Algorithms**:
- [Factoring](AlgoZoo/2.1-Factoring.ipynb) (Shor's Algorithm) - Breaks RSA cryptography
- [Discrete Logarithm](AlgoZoo/2.2-Discrete-log.ipynb) - Solves the discrete log problem
- [Pell's Equation](AlgoZoo/2.3-Pell's-Equation.ipynb) - Algebraic number theory
- [Principal Ideal](AlgoZoo/2.4-Principal-Ideal.ipynb), [Unit Group](AlgoZoo/2.5-Unit-Group.ipynb), [Class Group](AlgoZoo/2.6-Class-Group.ipynb)
- [Gauss Sums](AlgoZoo/2.7-Gauss-Sums.ipynb), [Primality Proving](AlgoZoo/2.8-Primality-Proving.ipynb)
- [Subset-sum](AlgoZoo/2.12-Subset-sum.ipynb), [Decoding](AlgoZoo/2.13-Decoding.ipynb)
- [Quantum Cryptanalysis](AlgoZoo/2.14-Quantum%20Cryptanalysis.ipynb)

### 2. Oracular Algorithms
**Core Mechanism**: Amplitude Amplification and Quantum Walks

Query complexity algorithms that provide speedups for black-box problems through quantum interference.

**Featured Algorithms**:
- [Searching](AlgoZoo/3.1-Searching.ipynb) (Grover's Algorithm) - Quadratic speedup for unstructured search
- [Deutsch-Jozsa](AlgoZoo/3.5-Deutsch-Jozsa.ipynb), [Bernstein-Vazirani](AlgoZoo/3.4-Bernstein-Vazirani.ipynb) - Oracle query separation
- [Abelian Hidden Subgroup](AlgoZoo/3.2-Abelian%20Hidden%20Subgroup.ipynb), [Non-Abelian Hidden Subgroup](AlgoZoo/3.3-Non-Abelian%20Hidden%20Subgroup.ipynb)
- [Collision Finding and Element Distinctness](AlgoZoo/3.14-Collision%20Finding%20and%20Element%20Distinctness.ipynb)
- [Welded Tree](AlgoZoo/3.13-Welded%20Tree.ipynb) - Exponential speedup over classical random walks
- [Graph Properties](AlgoZoo/3.11-Graph%20Properties%20in%20the%20Adjacency%20Matrix%20Model.ipynb) - Matrix and list models
- [Pattern Matching](AlgoZoo/3.9-Pattern%20matching.ipynb), [Formula Evaluation](AlgoZoo/3.6-Formula%20Evaluation.ipynb)
- [Matrix Rank](AlgoZoo/3.25-Matrix%20Rank.ipynb), [Matrix Commutativity](AlgoZoo/3.16-Matrix%20Commutativity.ipynb)

### 3. Approximation and Simulation Algorithms
**Core Mechanism**: Direct Quantum Simulation and Phase Estimation

Leveraging quantum computers as quantum systems to simulate other quantum systems and compute complex mathematical objects.

**Featured Algorithms**:
- [Simulating Quantum Hamiltonian Dynamics](AlgoZoo/4.1-Simulating%20Quantum%20Hamiltonian%20Dynamics.ipynb)
- [Preparing Eigenstates and Thermal States](AlgoZoo/4.2-Preparing%20Eigenstates%20and%20Thermal%20States.ipynb)
- [Knot Invariants](AlgoZoo/4.3-Knot%20Invariants.ipynb), [Three-manifold Invariants](AlgoZoo/4.4-Three-manifold%20Invariants.ipynb)
- [Partition Functions](AlgoZoo/4.5-Partition%20Functions.ipynb), [Zeta Functions](AlgoZoo/4.6-Zeta%20Functions.ipynb)
- [Simulated Annealing](AlgoZoo/4.8-Simulated%20Annealing.ipynb)
- [Matrix Powers](AlgoZoo/4.10-Matrix%20Powers.ipynb), [Probabilistic Sampling](AlgoZoo/4.11-Probabilistic%20Sampling.ipynb)

### 4. Optimization and Machine Learning Algorithms
**Core Mechanism**: Variational Methods and Quantum-Classical Hybrid Approaches

Near-term quantum algorithms for optimization problems and machine learning applications.

**Featured Algorithms**:
- [Quantum Approximate Optimization](AlgoZoo/5.3-Quantum%20Approximate%20Optimization.ipynb) (QAOA)
- [Adiabatic Algorithms](AlgoZoo/5.2-Adiabatic%20Algorithms.ipynb)
- [Linear Systems](AlgoZoo/5.8-Linear%20Systems.ipynb) (HHL Algorithm)
- [Machine Learning](AlgoZoo/5.10-Machine%20Learning.ipynb), [Tensor Principal Component Analysis](AlgoZoo/5.11-Tensor%20Principal%20Component%20Analysis.ipynb)
- [Semidefinite Programming](AlgoZoo/5.5-Semidefinite%20Programming.ipynb), [Convex Optimization](AlgoZoo/5.6-Convex%20Optimization.ipynb)
- [Solving Linear Differential Equations](AlgoZoo/5.12-Solving%20Linear%20Differential%20Equations.ipynb)
- [Computing the Principal Eigenvector](AlgoZoo/5.15-Computing%20the%20Principal%20Eigenvector.ipynb)
- [Approximating Nash Equilibria](AlgoZoo/5.16-Approximating%20Nash%20Equilibria.ipynb)

## 🎯 Key Features

- **Comprehensive Coverage**: 100+ quantum algorithms organized by category
- **Educational Focus**: Clear explanations of theoretical foundations and practical applications
- **Interactive Notebooks**: Jupyter notebooks with mathematical derivations and explanations
- **Markdown Versions**: Every algorithm has both `.ipynb` and `.md` formats for easy viewing
- **Structured Learning Path**: From introductory concepts to advanced applications
- **WorkBooks**: Practice-oriented notebooks for hands-on learning (2.1-2.4 WorkBook series)

## 🚀 Getting Started

### Prerequisites
```bash
# Install Jupyter Notebook
pip install jupyter notebook

# Optional: Install quantum computing frameworks
pip install qiskit cirq pennylane
```

### Exploring the Repository

1. **Start with the Introduction**: Begin with [1-Introduction.ipynb](1-Introduction.ipynb) to understand the landscape
2. **Choose Your Path**: Select a category that interests you (Algebraic, Oracular, Simulation, or Optimization)
3. **Deep Dive**: Explore specific algorithms in the `AlgoZoo/` directory
4. **Practice**: Use the WorkBook series (2.1-2.4) for hands-on exercises

### Quick Navigation
- Browse the [AlgoZoo Index](AlgoZoo/1-Index.ipynb) for a complete list of algorithms
- Check [BigBook.ipynb](BigBook.ipynb) for a consolidated view

## 📖 How to Use This Repository

### For Students
- Start with the numbered introduction notebooks (1-1.4)
- Work through the WorkBook series for practice
- Reference specific algorithms in AlgoZoo as needed

### For Researchers
- Jump directly to AlgoZoo for specific algorithm implementations
- Use the markdown versions for quick reference
- Explore the mathematical foundations and complexity analyses

### For Developers
- Examine algorithm implementations for practical applications
- Adapt code examples for your quantum computing framework of choice
- Use as a reference for quantum algorithm design patterns

## 🌟 What Makes Quantum Algorithms Special?

Quantum algorithms aren't just "faster classical algorithms." They fundamentally exploit:

1. **Superposition**: Processing multiple states simultaneously
2. **Entanglement**: Correlations that have no classical analog
3. **Interference**: Amplifying correct answers while canceling incorrect ones

The goal of every quantum algorithm is to choreograph these quantum effects so that wrong answers destructively interfere while the correct answer constructively amplifies.

## 📝 Algorithm Index

### Complete Algorithm List
See [AlgoZoo/1-Index.md](AlgoZoo/1-Index.md) for the complete catalog with over 100 algorithms including:
- Number theory and cryptography
- Search and optimization
- Graph problems
- Linear algebra
- Machine learning
- Quantum simulation
- And many more specialized applications

## 🤝 Contributing

This is an educational resource documenting the current state of quantum algorithms. Contributions, corrections, and improvements are welcome!

## 📜 License

See [LICENSE](LICENSE) for details.

## 🔗 References

This collection is inspired by and references:
- The Quantum Algorithm Zoo (Stephen Jordan)
- Quantum Computation and Quantum Information (Nielsen & Chuang)
- Current research papers in quantum computing

## 🎓 About

This repository serves as a comprehensive educational resource for anyone interested in quantum computing, from undergraduate students to researchers exploring the field. Each algorithm is presented with mathematical rigor while remaining accessible to those with a basic understanding of quantum mechanics and linear algebra.

---

**Note**: This is a living document. Quantum computing is a rapidly evolving field, and new algorithms and techniques are being developed continuously. Check [X-FutureAlgorithms.ipynb](AlgoZoo/X-FutureAlgorithms.ipynb) for emerging directions in quantum algorithm research.
