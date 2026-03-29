<div align="center">

# 🐍 Snake AI Reinforcement Learning

[![Python](https://img.shields.io/badge/Python-3.8+-blue.svg?logo=python&logoColor=white)](https://www.python.org)
[![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?logo=pytorch&logoColor=white)](https://pytorch.org/)
[![Pygame](https://img.shields.io/badge/Pygame-f0d843?logo=python&logoColor=black)](https://www.pygame.org/)

**An autonomous AI agent that learns to play the classic game of Snake using Deep Reinforcement Learning (Deep Q-Learning).**

</div>

---

## 🧠 How It Works

The AI relies on a **Deep Q-Network (DQN)** built via PyTorch. It doesn't know the rules of the game at the start; instead, it observes the environment and receives a reward based on its actions.
- 🍏 **Reward Policy:** `+10` for finding food, `-10` for a wall or body collision.
- 🔍 **State Observation:** The AI strictly analyzes its surroundings via an 11-dimensional state vector (Danger Straight/Right/Left, move direction, food relative location).
- 🎲 **Epsilon-Greedy Strategy:** In the beginning, the snake moves randomly to map out its environment. Over time, it starts exclusively trusting the Neural Network.

## 🛠️ Project Architecture

```text
Snake-AI-RL/
├── model/              # Directory where trained models are saved (.pth files)
├── agent.py            # Main RL agent, game loop, and training logic
├── helper.py           # Real-time training visualization tool
├── model.py            # Neural network architecture and QTrainer
├── requirements.txt    # Python dependencies
└── snake_game.py       # Custom Pygame environment modified for AI
```

| File | Description |
| ---- | ----------- |
| `agent.py` | 🎮 The main driver. Executes the game loop, parses the state, and directs "short" vs "batch" memory training. |
| `model.py` | 🧬 Defines the `Linear_QNet` PyTorch model alongside a custom `QTrainer` optimizer utilizing MSELoss and Adam. |
| `snake_game.py` | 🖼️ A custom pygame engine modified to execute single steps `play_step(action)` instead of standard continuous human loops. |
| `helper.py` | 📈 A Matplotlib plotting module that visualizes the AI's training success rate in real-time. |

## 🚀 Installation & Usage

1. **Clone the repository:**
   ```bash
   git clone https://github.com/Mayankg-13/Snake-AI-RL.git
   cd Snake-AI-RL
   ```

2. **Install the dependencies:**
   It is recommended to run this in a virtual environment.
   ```bash
   pip install -r requirements.txt
   ```

3. **Start the AI Training:**
   ```bash
   python agent.py
   ```

---
<div align="center">
  <i>Watch the plotted graph—things get exciting around the 80th attempt when the AI stops taking random routes!</i>
</div>
