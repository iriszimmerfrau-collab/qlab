<p align="center">
  <img src="favicon.png" width="80" alt="QuantumLab logo" />
</p>

<h1 align="center">QuantumLab</h1>

<p align="center">
  <em>Build quantum circuits. Watch qubits dance. Learn the magic behind quantum computing.</em>
</p>

<p align="center">
  <a href="https://iriszimmerfrau-collab.github.io/qlab/">
    <img src="https://img.shields.io/badge/Try_it_live-QuantumLab-7c4dff?style=for-the-badge&logo=flutter&logoColor=white" alt="Live Demo" />
  </a>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Flutter-3.11-02569B?logo=flutter" alt="Flutter" />
  <img src="https://img.shields.io/badge/Dart-3.11-0175C2?logo=dart" alt="Dart" />
  <img src="https://img.shields.io/badge/Firebase-Auth_%2B_Firestore-FFCA28?logo=firebase&logoColor=black" alt="Firebase" />
  <img src="https://img.shields.io/badge/Tests-205_passing-4caf50" alt="Tests" />
  <img src="https://img.shields.io/badge/License-Proprietary-lightgrey" alt="License" />
</p>

---

## What is QuantumLab?

**QuantumLab** is an interactive quantum computing playground built with Flutter. It runs entirely in your browser — no Python, no Jupyter, no installs. Drag gates onto qubits, hit **Run**, and instantly see probabilities, measurement counts, and Bloch sphere rotations.

Whether you're a curious beginner wondering *"what even is a qubit?"* or a student brushing up on CNOT gates before an exam, QuantumLab makes quantum circuits feel approachable and fun.

---

## Features

### Circuit Builder

Build quantum circuits visually on an interactive grid. Tap a gate from the palette, tap a qubit — done.

- **8 quantum gates** — H, X, Y, Z, S, T, CNOT, SWAP
- **Up to 8 qubits** — scale your circuits from simple to complex
- **Real-time simulation** — probabilities update as you build, no "compile" step
- **Measurement sampling** — run 1024 shots and see realistic count distributions
- **Undo stack** — 30-level undo with `Ctrl+Z`, because mistakes happen
- **Keyboard shortcuts** — `H` for Hadamard, `X` for Pauli-X, `R` to run, `Esc` to deselect
- **Export to real frameworks** — generate Qiskit, Cirq, or OpenQASM code (Pro)

### Bloch Sphere

A real-time 3D Bloch sphere visualization that tracks individual qubit states as you build your circuit. See exactly where your qubit lives on the sphere — |0⟩ at the north pole, |1⟩ at the south, and all the superpositions in between.

### Probability Histogram

Animated bar chart showing measurement probability distributions with exact amplitudes, plus sampling-based count chips after running measurements.

### Learn Quantum

**15 guided lessons** that teach quantum computing from scratch:

| Track | Lessons | What you'll learn |
|-------|---------|-------------------|
| **Quantum Basics** | 10 lessons | Qubits, superposition, entanglement, gates, measurement |
| **OpenQASM** | 5 lessons | Write quantum assembly code from scratch |

Each lesson has explanations, interactive circuit demos, quizzes, and hints. Progress syncs across devices when signed in.

### QASM Editor

A built-in OpenQASM 2.0 editor with syntax highlighting and live execution. Write quantum assembly, hit Run, see results — all in the browser.

```qasm
OPENQASM 2.0;
qreg q[2];

h q[0];
cx q[0], q[1];

measure q;
```

### PFQVS Engine

The **Probabilistic Finite Quantum Virtual State** engine — QuantumLab's custom quantum simulation backend. Full complex-amplitude state vector simulation with exact probability computation.

---

## Tech Stack

| Layer | Tech |
|-------|------|
| **Framework** | Flutter 3.11 (Web, Android, iOS) |
| **State** | Riverpod 2 (NotifierProvider pattern) |
| **Routing** | go_router with hash-based URLs |
| **Charts** | fl_chart for probability histograms |
| **Auth** | Firebase Auth (Google sign-in + anonymous) |
| **Database** | Cloud Firestore with offline persistence |
| **Animations** | flutter_animate for micro-interactions |
| **Simulation** | Custom complex-number linear algebra engine |

---

## Architecture

```
lib/
 ├── engine/          # Quantum simulation core
 │   ├── quantum_computer.dart   # State vector simulator
 │   ├── bloch.dart              # Bloch sphere math
 │   ├── qasm_parser.dart        # OpenQASM parser
 │   └── export.dart             # Qiskit/Cirq/QASM export
 ├── models/          # Data models (Circuit, Gate, Lesson)
 ├── providers/       # Riverpod state management
 ├── services/        # Firebase service layer
 └── ui/
     ├── screens/     # 7 screens (Home, Builder, Lessons, etc.)
     └── widgets/     # Reusable components (Grid, Palette, Bloch)
```

The simulation engine uses **pure Dart** — no native dependencies, no WASM, no external math libraries. Complex number arithmetic, tensor products, and matrix operations are all hand-rolled for maximum portability.

---

## Keyboard Shortcuts

| Key | Action |
|-----|--------|
| `H` | Select Hadamard gate |
| `X` | Select Pauli-X gate |
| `Y` | Select Pauli-Y gate |
| `Z` | Select Pauli-Z gate |
| `C` | Select CNOT gate |
| `R` | Run measurement |
| `Ctrl+Z` | Undo |
| `Delete` | Clear circuit |
| `Esc` | Deselect gate |

---

## Responsive Design

QuantumLab adapts to any screen size:

- **Wide (>1100px)** — Circuit grid + Bloch sphere + histogram side-by-side
- **Medium (700–1100px)** — Circuit grid + stacked visualizations panel
- **Narrow (<700px)** — Stacked layout with tabbed histogram/Bloch switching

---

<p align="center">
  Built with <img src="https://img.shields.io/badge/-Flutter-02569B?logo=flutter&logoColor=white" alt="Flutter" height="20" style="vertical-align: middle" /> and a mass superposition of caffeine states.
</p>
