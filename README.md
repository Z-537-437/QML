# QML vs. Classical Models: Algorithms, Datasets, and Generalization Metrics

## 1. Detailed Classification and Explanation of QML Algorithms

### 1.1 Basic quantum algorithms

| Algorithm name                   | Abbreviation | Date submitted | Core principles                                              | Time complexity                                    | Typical applications                                         | References |
| -------------------------------- | ------------ | -------------- | ------------------------------------------------------------ | -------------------------------------------------- | ------------------------------------------------------------ | ---------- |
| **Grover's Algorithm**           | Grover       | 1996           | Amplify the amplitude; mark the target state using Oracle; repeatedly apply diffusion transformations to enhance the amplitude of the target state | $O(\sqrt{N})$  vs Classic$O(N)$                    | Brute-force database searches, cryptanalysis (e.g. DES key searches) | [11]       |
| **Bernstein-Vazirani Algorithm** | BV           | 1993           | Using quantum parallelism to determine a hidden binary string in a single query | $O(1)$ vs Classic $O(n)$                           | Quantum circuit diagnostics, verification of quantum cryptographic protocols | [12]       |
| **Shor's Algorithm**             | Shor         | 1994           | Convert the factorisation of integers into a problem of finding periods, and use QFT to extract the periods | $O((\log N)^2 \log \log N)$ vs Classic Exponential | RSA cryptanalysis, the discrete logarithm problem            | [13]       |
| **Quantum Fourier Transform**    | QFT          | 1994           | The discrete Fourier transform of a quantum state maps the computational basis to frequency space | $O(n^2)$ vs  classic $O(n2^n)$                     | Shor’s algorithm, phase estimation, quantum signal processing | [14]       |

### 1.2 Quantum supervised learning algorithms

| Algorithm name                                   | Abbreviation | Core principles                                              | Quantum advantage                                            | Typical applications                                       | References |
| ------------------------------------------------ | ------------ | ------------------------------------------------------------ | ------------------------------------------------------------ | ---------------------------------------------------------- | ---------- |
| **Quantum Support Vector Machine**               | QSVM         | Computing nuclear functions using quantum circuits $K_{ij} = \|\langle \phi(x_i) \| \phi(x_j) \rangle\|^2$，Computing inner products in exponential Hilbert spaces | Using quantum superposition states to implicitly map to high-dimensional space | Image recognition and classification tasks                 | [8]        |
| **Variational Quantum Classification Algorithm** | VQCA         | A parametric quantum circuit  𝑈(𝜃)   encodes data; the parameters are adjusted via a classical optimiser to minimise the loss function | Enhancing the expressive power of models using quantum entanglement and superposition | Binary classification and multi-class classification tasks | [22]       |
| **Quantum Neural Network**                       | QNN          | The quantum neuron model, consisting of an encoding circuit $U_\phi$ and a variational circuit   $U_\theta$  , evolves as follows:$ \|\psi(\theta)\rangle = U_\theta U_\phi \|0\rangle $ | Operating within a Hilbert space may help avoid the vanishing gradient problem (subject to specific design) | Image recognition, pattern recognition                     | [10]       |
| **PegasosQSVM**                                  | -            | A variant of QSVM that combines the Pegasos algorithm (primitive dual gradient descent) and supports large-scale datasets | Improved scalability, with support for sparse solutions      | Large-scale classification tasks                           | [9]        |

### 1\.3 Quantum Deep Learning Algorithms

|Algorithm Name|Abbreviation|Architectural Features|Core Innovation|Typical Applications|References|
|---|---|---|---|---|---|
|**Quantum Convolutional Neural Network**|QCNN|Alternate quantum convolutional layers \(local unitary transformations\) and pooling layers \(measurement discard or conditional operations\)|Logarithmic circuit depth, translation invariance, strong noise resistance|Quantum state recognition, image classification, signal processing|\[26\]|
|**Quantum Long Short\-Term Memory**|QLSTM|Implement the gate mechanism of LSTM with quantum circuits: $f_t = U_{\theta_f}(x_t, h_{t-1})$, $i_t = U_{\theta_i}(x_t, h_{t-1})$, etc\.|Model temporal dependencies using quantum entanglement, potentially alleviating vanishing gradients|Time series prediction, natural language processing, quantum signal processing|\[22\]|
|**Quantum Generative Adversarial Network**|QGAN|Both generator $U_G(\theta)$ and discriminator $U_D(\phi)$ are quantum circuits, trained adversarially|Capable of learning quantum data distributions and generating realistic quantum states|Quantum data generation, distribution learning|\[137\]|
|**Quantum Boltzmann Machine**|QBM|Quantum thermal state $\rho_\lambda = \frac{e^{-\beta H(\lambda)}}{\text{Tr}(e^{-\beta H(\lambda)})}$ defined by Hamiltonian $H(\lambda) = H_Z + H_X$|Utilize quantum tunneling effect to potentially escape local optima|Quantum physical system modeling, quantum data learning|\[90\]|

### 1\.4 Quantum Reinforcement Learning Algorithms

|Algorithm Name|Abbreviation|Architectural Features|Learning Mechanism|Typical Applications|References|
|---|---|---|---|---|---|
|**Quantum Q\-Learning**|QQL|State\-action pairs $(s,a)$ are encoded into parameterized circuits $U_Q(\theta_{s,a})$, and Q\-values are obtained from measurement results|TD update: $Q(s,a) \leftarrow Q(s,a) + \alpha[r + \gamma \max_{a'} Q(s',a') - Q(s,a)]$|Maze navigation, grid world tasks|\[21\]|
|**Quantum Policy Gradient**|QPG|Policy $\pi_\theta(a \mid s)$ is encoded by quantum circuits, and actions are sampled from measurement results|Policy gradient: $\nabla_\theta J(\theta) = \mathbb{E}[\nabla_\theta \log \pi_\theta(a \mid s) Q^\pi(s,a)]$|Continuous control, policy optimization|\[26\]|

### 1\.5 Quantum Optimization Algorithms

|Algorithm Name|Abbreviation|Core Principle|Mathematical Expression|Typical Applications|References|
|---|---|---|---|---|---|
|**Quantum Approximate Optimization Algorithm**|QAOA|Alternately apply problem Hamiltonian $H_C$ and mixing Hamiltonian $H_M$, and solve combinatorial optimization problems via parameter optimization|$|\psi(\gamma,\beta)\rangle = \prod_{j=1}^p e^{-i\beta_j H_M} e^{-i\gamma_j H_C} |+\rangle^{\otimes n}$|Max-Cut, combinatorial optimization problems|[35]|
|**Variational Quantum Eigensolver**|VQE|Prepare ansatz states with parameterized circuits, measure the expected energy value, and minimize energy via classical optimization|$E(\theta) = \langle \psi(\theta) \|H \|\psi(\theta) \rangle$|Quantum chemistry, material simulation|[67]|

---

## 2\. Detailed Explanation of Quantum Datasets

### 2\.1 Specialized Quantum Datasets

| Dataset Name                            | Source Institution    | Data Type                                       | Scale                                                        | Encoding Scheme                                  | Applicable Tasks                                             | Key Features                                                 | References |
| --------------------------------------- | --------------------- | ----------------------------------------------- | ------------------------------------------------------------ | ------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ | ---------- |
| **QDataSet**                            | Independent Research  | Classical data + quantum circuit representation | Multiple available scales                                    | Angle encoding, amplitude encoding, IQP encoding | Classification, regression, generative modeling              | Provides standardized train-test splits, includes metadata describing the encoding process, and supports direct loading via Qiskit | [88]       |
| **PennyLane Quantum Datasets**          | Xanadu                | Classical data, molecular data                  | Small scale                                                  | Multiple built-in encoding schemes               | Teaching, benchmark testing, hybrid model validation         | Includes the moon dataset (binary classification), H₂ molecule, LiH molecule and other resources, with seamless integration with PennyLane | [87]       |
| **Open Quantum Data Commons (OpenQDC)** | Open Source Community | Molecular geometry data                         | 1.5 billion+ geometric structures, 70+ atomic species, 250+ quantum chemistry methods | N/A                                              | Quantum chemistry, material simulation, density functional theory verification | Ultra-large scale, standardized metadata, native Python API support, and storage in high-efficiency formats | [79]       |

### 2\.2 Quantumized Versions of Classical Datasets

|Original Dataset|Purpose of Quantumized Version|Common Encoding Methods|**Effect / Model Performance**|Typical Reference Literatures|
|---|---|---|---|---|
|**MNIST**|Handwritten digit recognition|Amplitude encoding, angle encoding|Used to test the performance of hybrid convolutional structures \(Parameterized Quantum Circuits as sliding kernels\)\.|\[31\], \[40\], \[134\]|
|**Iris**|Flower classification|Angle encoding, basic encoding|Used to test basic classification models such as Variational Quantum Classifier \(VQC\)\.|\[134\]|
|**Fashion\-MNIST**|Clothing image classification|Amplitude encoding|Widely used in hybrid architecture and robustness evaluation, with the SHQCNN model achieving excellent performance on this dataset\.|\[113\], \[57\]|
|**CIFAR\-10/100**|Object recognition|Amplitude encoding, magnitude encoding|Used to evaluate the Balanced Quantum Neural Architecture Search \(BQNAS\)model, with accuracy rates reaching 97\.27% and 81\.36% respectively\.|\[132\]|
|**GossipCop/PolitiFact**|Fake news detection|Amplitude encoding|QMFND \(Quantum Multimodal Fusion Model\) uses these two text/multimodal datasets to detect fake news on social media\.|\[98\]|
|**Cardiovascular Disease Dataset**|Disease diagnosis|Angle encoding|QuCardio project, using cardiovascular disease data, achieved an accuracy of 97\.31%|\[94\]|
|**Breast Cancer Dataset**|Medical diagnosis|Amplitude encoding, angle encoding|Used to integrate quantum layers into CNN for diagnosis, demonstrating generalization ability on large\-scale medical data\.|\[125\]|
|**Potentially Hazardous Asteroids**|Planetary classification|\-|Classified asteroids using VQCA and PegasosQSVM, with an accuracy rate of 98\.11%\.|\[9\], \[122\]|

---

## 3\. Detailed Corresponding Relationships between QML and Traditional Models

### 3\.1 Supervised Learning Model Correspondence

|QML Model|Corresponding Traditional Model|
|---|---|
|**QSVM**|SVM \(Kernel Methods\)|
|**VQCA**|Logistic Regression / Shallow Neural Networks|
|**QNN**|Classical Neural Networks \(ANN/MLP\)|
|**PegasosQSVM**|Pegasos\-SVM|

### 3\.2 Deep Learning Model Correspondence

|QML Model|Corresponding Traditional Model|
|---|---|
|**QCNN**|Convolutional Neural Network \(CNN\)|
|**QLSTM**|Long Short\-Term Memory \(LSTM\)|
|**QGAN**|Generative Adversarial Network \(GAN\)|
|**QBM**|Boltzmann Machine|

### 3\.3 Reinforcement Learning Model Correspondence

|QML Model|Corresponding Traditional Model|
|---|---|
|**QQL**|Q\-Learning \(Tabular\)|
|**QPG**|Policy Gradient \(Policy Gradient Methods\)|

### 3\.4 Optimization Algorithm Correspondence

|QML Model|Corresponding Traditional Model|
|---|---|
|**QAOA**|Combinatorial Optimization Solvers \(e\.g\., Simulated Annealing\)|
|**VQE**|Classical Variational Methods|

---

## 4\. Generalization Ability Evaluation Metric System

|**Evaluation Metric Category**|**Specific Metrics / Performance**|**Evidence and Sources in the Document**|**Generalization Insight**|
|---|---|---|---|
|**Prediction Accuracy**|**98\.11%** \(Asteroid Classification\), **99\.58%** \(Image Classification\), **97\.27%** \(CIFAR\-10\)|Refer to the experimental results of **VQCA \[122\]**, **SHQCNN \[113\]** and **BQNAS \[132\]** described in Section 7\.2\.|The most intuitive reflection of generalization ability, proving that the model can correctly process unseen test samples\.|
|**Robustness to Noise**|Great robustness|Explicitly mentioned in the descriptions of **QMFND \[98\]** \(Fake News Detection\) and **SHQCNN \[113\]** that the models remain stable in the noisy environment of NISQ devices\.|Evaluate the generalization stability of the model on real, imperfect quantum hardware\.|
|**Parameter Efficiency**|The number of parameters is reduced by **more than 20%.**|Refer to the research results of **EQNAS \[126\]**, which significantly reduced parameters by optimizing PQC structure via evolutionary algorithms\.|In accordance with Occam's Razor principle, fewer parameters typically indicate better generalization ability and help avoid overfitting.|
|**Training Stability**|Improved adversarial training stability|Refer to **ILL\-QGAN \[129\]**, which solved the common vanishing gradient or instability problems in classical GAN training through hybrid architecture\.|Ensure that the model can converge to the global optimum under different dataset distributions\.|
|**Computational Time Reduction**|Simulation time reduced by **more than** **68,000 times**|Refer to the description of quantum inner product circuit simulation optimization **\[13\]** in Section 7\.2\.|Measure the potential advantages of quantum algorithms in computational complexity during large\-scale data generalization\.|
|**Quantum Dropout**|Improved generalization|The document explicitly mentions that **\[116\]** introduced Quantum Dropout technology\.|**Key Evidence:** The text explicitly states that this technique is specifically designed to "improving the generalization of the model".|
|**Sample Efficiency**|Maintain high accuracy \(**90\.1%**\) in low\-data environments|Refer to the performance of **H\-QNN \[111\]** when processing small\-scale datasets\.|Prove that QML models have stronger generalization potential than traditional deep learning in data\-scarce fields \(e\.g\., medical care\)\.|

