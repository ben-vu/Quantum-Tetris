
# Quantum Tetris

Quantum Tetris is a browser-based Tetris game enhanced with real quantum randomness and quantum algorithms for gameplay dynamics. It leverages Qiskit and Quokka (a cloud-based quantum simulator) to introduce quantum randomness into piece selection and dynamic speed control using Grover's algorithm and Quantum Phase Estimation (QPE).

## 🚀 Features

- **Quantum Piece Selection**: Uses a 6-qubit quantum circuit to randomly select Tetris pieces with true quantum randomness.
- **Quantum Speed Control**:
  - **Grover's Algorithm**: Applies Grover's search to determine a probabilistic speed multiplier between 0.5× and 2.0×.
  - **Quantum Phase Estimation (QPE)**: Offers more precise control over the speed using estimated quantum phases.
- **Interactive Frontend**: Rendered in-browser with controls and speed visualisation.
- **Hybrid Backend**: JavaScript frontend communicates with Python via Jupyter Comm channels.

## 🧠 Requirements

- Python 3.x
- Jupyter Notebook or JupyterLab
- Installed Python packages:
  ```bash
  pip install qiskit numpy requests
  ```
- Internet connection (to access Quokka quantum simulator)

## ⚙️ How It Works

1. **Quantum Random Number Generator (QRNG)**:
   - A 6-qubit Hadamard circuit produces random numbers between 0–63.
2. **Grover-based Speed Feature**:
   - Marks 1–2 states randomly and applies Grover's algorithm to search.
   - Result determines game speed.
3. **Quantum Phase Estimation (QPE)**:
   - Controlled rotations derive a quantum phase for fine-grained speed control.
4. **Comm Messaging**:
   - JavaScript sends requests to Python for either piece selection or speed change.
   - Python returns results through Comm channels.

## 🎮 Controls

| Key       | Action             |
|-----------|--------------------|
| A / ←     | Move Left          |
| D / →     | Move Right         |
| S / ↓     | Soft Drop          |
| W / ↑     | Rotate             |
| Space     | Hard Drop          |
| P         | Pause              |
| Q         | Quantum Speed Boost|
| O         | Start Game         |

## 🧪 Quantum Integration Demo

When running inside Jupyter / Colab, click the **QUANTUM SPEED** button to trigger real-time quantum logic for adjusting game speed.

If no kernel is found, the game falls back to standard pseudo-random behavior.

## 📁 File Structure

- `main.ipynb`: Python + JS hybrid notebook that contains the full game logic.
- `quantum_engine.py`: (Optional) Contains helper functions for quantum logic.
- `README.md`: You're reading it.

## 📬 Notes

- Requires a kernel running Python in a Jupyter environment.
- Communication with Quokka is done over HTTP (self-signed certs are ignored).
- Use responsibly and enjoy the quantum twist on a classic game!

---

© 2025 Benjamin Vu
