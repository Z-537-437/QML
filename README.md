# QML vs. CML: A Unified Empirical Comparison

This research project conducts a performance comparison between **Quantum Machine Learning (QML)** and **Classical Machine Learning (CML)** across various supervised and reinforcement learning tasks.

------

## Project Contents

The project includes 7 representative model pairs covering classification and sequential decision-making tasks.

### 1. Supervised Learning Model Pairs

These models are evaluated using classification tasks on the **BAS (Bars and Stripes)** dataset.

Metrics: Accuracy , Precision , Recall , F1-Score , AUC-ROC , Training Eff.

| **Model Pair**                | **Quantum Model** | **Classical Model** |
| ----------------------------- | ----------------- | ------------------- |
| **QSVM vs SVM**               | QSVM              | SVM                 |
| **QNN vs ANN**                | QNN               | ANN                 |
| **PegasosQSVM vs PegasosSVM** | PegasosQSVM       | PegasosSVM          |
| **QCNN vs CNN**               | QCNN              | CNN                 |
| **QLSTM vs LSTM**             | QLSTM             | LSTM                |

### 2. Reinforcement Learning Model Pairs

These experiments involve navigation tasks within a **Hypercube** environment.

Metrics: Average Return , Win Rate , Stability , Params , Training Eff.

| **Model Pair** | **Quantum Agent**     | **Classical Agent** |
| -------------- | --------------------- | ------------------- |
| **QPG vs PG**  | QPG (Policy Gradient) | PG                  |
| **QQL vs QL**  | QQL (Q-Learning)      | QL (DQN)            |

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
   git clone https://anonymous.4open.science/r/QML-83A6
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