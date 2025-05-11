🎮 Quantum Tetris
Quantum Tetris is a browser-based twist on the classic game of Tetris, enhanced with real quantum randomness and quantum algorithms. It integrates Quokka, a cloud quantum simulator, to introduce unpredictable gameplay dynamics through QRNG, Grover's algorithm, and Quantum Phase Estimation.

🧠 Key Features
Quantum Random Number Generation (QRNG)
Uses a 6-qubit Hadamard circuit to randomly collapse states from 0 to 63.

Grover’s Algorithm for Speed Boosts
Grover-based oracle circuits are used to determine if the player should experience a slowdown or speed boost during gameplay.

Quantum Phase Estimation (QPE)
Offers fine-grained control over game speed using estimated quantum phases.

Real-Time Quantum-Classical Interaction
Communication between Python and JavaScript is managed via Jupyter kernel's Comm bridge.

📦 Dependencies
To run the game, you need:

Python 3.x

Jupyter Notebook / JupyterLab

Qiskit

Quokka-compatible backend (default is quokka3.quokkacomputing.com)

Install Qiskit using:

pip install qiskit


🚀 How to Play
Launch the game in a Jupyter Notebook.

Press O to start the game.

Use classic Tetris controls to move and rotate pieces:

A / ← : Move Left  
D / → : Move Right  
S / ↓ : Soft Drop  
W / ↑ : Rotate  
Space : Hard Drop  
P     : Pause  
Q     : Quantum Speed (Grover/QPE)  
O     : Start Game

Click the QUANTUM SPEED button or press Q to trigger quantum-based speed adjustments.

⚛️ Quantum Mechanics in the Game
Feature	Circuit Used	Effect on Game
Piece Collapse	6-qubit Hadamard ladder	Selects next tetromino using true QRNG
Speed Boost	Grover's algorithm with custom oracle	Increases or decreases speed dynamically
Precision Speed	Quantum Phase Estimation (QPE)	Maps phase to a precise speed multiplier

🌐 Quokka Integration
Quantum circuits are transpiled to OpenQASM 3 and executed remotely using Quokka:
send_to_quokka(dumps(circuit), count=1)

🧩 File Structure (Core Components)
qrng_0_to_63(): Generates a number from 0–63 using quantum measurement.

run_grover_speed_algorithm(): Marks target states to determine speed-up or slow-down.

qpe_speed_control(): Uses phase estimation to determine a fine-tuned speed factor.

comm.on_msg: Handles interaction between JS and Python kernel.

🖥️ UI Features
Real-time canvas-based game board

Dynamic speed bar visualization

Live score and quantum state display

Responsive controls for keyboard and quantum input

❗ Notes
If a Jupyter kernel is not available, the game falls back to classical randomness.

All communication with Quokka disables SSL verification (verify=False); avoid this in production environments.

📜 License
MIT License. Use at your own risk. Have fun experimenting with quantum-enhanced gameplay!
