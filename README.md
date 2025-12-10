# DSDM Research Report: Online Task-Free Continual Learning

This repository contains a comprehensive research summary and analysis of the paper **"Online Task-free Continual Learning with Dynamic Sparse Distributed Memory"**.

## 📄 Overview
[cite_start]Dynamic Sparse Distributed Memory (DSDM) is an associative, content-addressable memory model designed to solve catastrophic forgetting in neural networks[cite: 3, 5]. [cite_start]Unlike traditional models that require task boundaries or data replay, DSDM learns from non-stationary data streams in a single pass by dynamically adapting its memory structure[cite: 4].

## 🧠 How DSDM Works
[cite_start]The core mechanism relies on replacing global weight updates with a dynamic memory of sparse, distributed representations[cite: 6].

### 1. Dynamic Memory Structure
* [cite_start]**Initialization:** Unlike classical SDM which has a fixed size, DSDM starts with an empty memory and adds neurons dynamically as new patterns emerge[cite: 15].
* [cite_start]**Matrices:** The memory consists of an Address Matrix ($A$) for features and a Content Matrix ($C$) for labels[cite: 10, 11].

### 2. The Learning Algorithm
[cite_start]DSDM processes each sample ($x_t, y_t$) once using a metric called **Recursive Temperature (RT)**[cite: 18, 22].
* [cite_start]**New Neuron Creation:** If the distance to the best matching unit ($d_{BMU}$) is greater than $RT$, a new neuron is created to store the novel pattern[cite: 27, 28].
* [cite_start]**Distributed Update:** If $d_{BMU} \le RT$, the information is distributed among existing neurons using a softmin weighting function, refining knowledge without overwriting it[cite: 29, 30].

### 3. Memory Pruning
[cite_start]To maintain efficiency, DSDM applies a density-based pruning strategy (Local Outlier Factor) to remove redundant neurons when the memory capacity is reached[cite: 33, 34].

## 📊 Key Results & Experiments
The report analyzes DSDM's performance across several benchmarks:
* [cite_start]**Split MNIST:** Achieved **94.0%** accuracy, significantly outperforming classical SDM (74.2%) and deep learning methods like CN-DPM[cite: 82].
* [cite_start]**Split CIFAR-10:** Reached **67.0%** last accuracy in online settings, surpassing Candidate Voting (62.9%)[cite: 88].
* [cite_start]**Efficiency:** Demonstrates state-of-the-art performance without backpropagation or repeated epochs[cite: 82, 130].

## 📂 Repository Contents
* **`DSDM_Report.pdf`**: The full 3-5 page summary report detailing the architecture, experiments, and limitations.

---
*Note: This report was prepared as part of the Research Assistant (AI) technical assessment.*
