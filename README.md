# 🧠 Chess Challenge – QAOA Quantum Optimization

This repository contains the code developed for the **MQST Qiskit Fall Fest Chess Challenge**.  
The goal of this challenge is to explore **quantum optimization algorithms** (QAOA) by solving classical chess puzzles — starting from **rooks**, extending to **bishops**, and finally combining both into the **queens problem**.

---

## ♟️ Overview

The project reformulates the **non-attacking chess piece placement problem** as a **quantum optimization problem**.  
Each square of an $N \times N$ chessboard is represented by a **qubit**, where:

- `|1⟩` indicates a piece is placed,
- `|0⟩` indicates an empty square.

A **Hamiltonian** encodes the rules of the puzzle:
- One-body terms reward adding a valid piece.
- Two-body terms penalize configurations where pieces attack each other.

The **QAOA (Quantum Approximate Optimization Algorithm)** is then used to find the **ground state** (lowest-energy configuration), corresponding to valid puzzle solutions.

---

## 🧩 Implemented Problems

### 1. Rooks Puzzle
- Classical brute-force solver (`classical_rooks`).
- Quantum Hamiltonian formulation for rooks’ horizontal/vertical conflicts.
- QAOA implementation and visualization of results for 3×3 and 4×4 boards.
- Degeneracy breaking (“tilted board”) via biased one-body terms.

### 2. Bishops Puzzle
- Brute-force solver for maximum non-attacking bishops.
- Hamiltonian formulation including diagonal conflicts.
- Tilt term (`δ`) added to break degeneracy and favor specific placements.
- QAOA implementation and comparison with classical results.

### 3. Queens Puzzle
- Combines rook and bishop Hamiltonians to handle all attack directions.
- Classical brute-force validation.
- Quantum solution via QAOA for 3×3 and 4×4 boards.

---

## ⚙️ Installation

To reproduce the results, install the required dependencies:

```bash
pip install --upgrade pip
pip install numpy==2.3.4
pip install scipy==1.16.2
pip install matplotlib==3.10.7
pip install jupyter
pip install "qiskit[visualization]==2.2"
pip install qiskit_algorithms==0.4.0
pip install qiskit_aer==0.17.2
pip install qiskit_ibm_runtime==0.41.1
pip install qiskit_ibm_transpiler==0.14.3
