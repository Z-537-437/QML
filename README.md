# QML vs. CML: A Unified Empirical Comparison

This research project conducts a performance comparison between **Quantum Machine Learning (QML)** and **Classical Machine Learning (CML)** across various supervised and reinforcement learning tasks.

------

## Project Contents

The project includes 7 representative model pairs covering classification and sequential decision-making tasks.

### 1. Supervised Learning Model Pairs

These models are evaluated using classification tasks on the **BAS (Bars and Stripes)** dataset.

| **Model Pair**                | **Quantum Model** | **Classical Model** | **Primary Metrics**           |
| ----------------------------- | ----------------- | ------------------- | ----------------------------- |
| **QSVM vs SVM**               | QSVM              | SVM                 | Accuracy, F1-Score, AUC-ROC   |
| **QNN vs ANN**                | QNN               | ANN                 | Accuracy, Precision, Recall   |
| **PegasosQSVM vs PegasosSVM** | PegasosQSVM       | PegasosSVM          | Accuracy, Training Efficiency |
| **QCNN vs CNN**               | QCNN              | CNN                 | Precision, Noise Robustness   |
| **QLSTM vs LSTM**             | QLSTM             | LSTM                | Sequence Generalization       |

### 2. Reinforcement Learning Model Pairs

These experiments involve navigation tasks within a **Hypercube** environment.

| **Model Pair** | **Quantum Agent**     | **Classical Agent** | **Primary Metrics**      |
| -------------- | --------------------- | ------------------- | ------------------------ |
| **QPG vs PG**  | QPG (Policy Gradient) | PG                  | Average Return, Win Rate |
| **QQL vs QL**  | QQL (Q-Learning)      | QL (DQN)            | Stability, Params Count  |

------

## Environment Setup

### Requirements

The project is built on the **PennyLane** framework and seamlessly integrates with the **PyTorch** deep learning interface.

- **Python**: Version 3.7+ is recommended.
- **Quantum Computing Framework**: PennyLane.
- **Deep Learning Framework**: PyTorch.
- **Classical Model Library**: Scikit-learn.
- **Reinforcement Learning Environment**: Gymnasium.
- **Quantum Simulation**: Noiseless State-vector Simulator.

### Setup Steps

1. **Clone the Repository**

   Bash

   ```
   git clone https://anonymous.4open.science/r/QML-C2FE/
   ```

2. **Install Dependencies**

   Bash

   ```
   pip install pennylane torch scikit-learn gymnasium
   ```

------

## Code Reproduction and Usage

### Running Code Files

All experiments are provided as Jupyter Notebooks (`.ipynb`) for interactive experimentation and result visualization. You can run the following files based on your needs:

- **Reproduce Supervised Learning Comparisons:**
  - Run `QSVM vs SVM.ipynb`
  - Run `QNN vs ANN.ipynb`
  - Run `QCNN vs CNN.ipynb`
  - Run `QLSTM vs LSTM.ipynb`
  - Run `PegasosQSVM vs PegasosSVM.ipynb`
- **Reproduce Reinforcement Learning Comparisons:**
  - Run `QQL vs QL.ipynb`
  - Run `PG vs QPG.ipynb`

### Dataset Descriptions

- **BAS Dataset**: Contains $N \times N$ binary images (horizontal or vertical stripes) and supports the injection of adjustable normalized Gaussian noise.
- **Hypercube Environment**: A custom environment following Gymnasium standards, where the state space is defined by the vertices of an $n$-dimensional hypercube (with $n=6$ used in experiments).