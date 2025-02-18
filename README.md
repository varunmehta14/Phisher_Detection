# Phisher Detection in Ethereum Transaction Networks

## Overview
This project focuses on detecting phishing addresses in the Ethereum blockchain using **Graph Convolutional Networks (GCNs)**. Ethereum transaction networks are vast and complex, making it challenging to identify fraudulent addresses. This research introduces an efficient, scalable approach utilizing **RiWalk embeddings, sparse operations, and knowledge distillation** to improve detection accuracy while reducing computational overhead.



## Features
- **Graph-based phishing detection**: Uses **Graph Convolutional Networks (GCNs)** to classify phishing and non-phishing addresses.
- **Efficient node embeddings**: Leverages **RiWalk**, a role-based random-walk algorithm, to extract graph-based features.
- **Sparse operations for scalability**: Optimized GCNs using sparse tensors for memory efficiency.
- **Knowledge distillation for model compression**: Reduces model size by 50% while maintaining high accuracy.
- **High precision and recall**: Improves phishing detection accuracy over baseline methods (Logistic Regression, Random Forest).

## Technologies Used
- **Python**
- **PyTorch**
- **NetworkX**
- **RiWalk** (for node embeddings)
- **Scikit-learn**
- **TensorFlow TPU environment** (for training efficiency)

## Methodology
### 1. Data Collection & Preprocessing
- Utilized Ethereum transaction dataset (3M nodes, 13.5M edges, 1165 phishing labels).
- Converted Ethereum transaction history into a graph representation.
- Applied **RiWalk** embeddings to generate node features.

### 2. Baseline Models
- **Logistic Regression**: Established early benchmark with basic linear classification.
- **Random Forest**: Applied ensemble learning for feature importance.
- Results showed **high accuracy but low recall** due to data imbalance.

### 3. Graph Convolutional Networks (GCNs)
- Designed multiple GCN architectures:
  - **2-layer GCN**: Insufficient depth, low recall.
  - **4-layer Mid-Size GCN** (Best performing model): Balanced recall and precision.
  - **10-layer Large GCN**: Overfitting observed, diminishing returns.
- Implemented **Batch Normalization** and **Dropout** for improved stability.

### 4. Sparse Operations
- Converted adjacency matrix into **sparse tensor** to reduce memory usage.
- Improved computational efficiency by **16%** while preserving accuracy.

### 5. Knowledge Distillation
- **Teacher model**: 256 features per layer (full-size GCN).
- **Student model**: 192 → 128 features per layer (compressed GCN).
- Achieved **50% model size reduction** while maintaining high precision and recall.

## Results
- **GCNs significantly outperformed traditional models** (Random Forest, Logistic Regression).
- **Sparse operations reduced training time by 16%**.
- **Knowledge distillation retained 99% of accuracy with 50% fewer parameters**.
- **Best Model: Mid-Size 4-layer GCN** with **high recall and precision**.


## Future Enhancements
- Extend dataset with real-time phishing updates.
- Integrate **self-supervised learning** for more robust embeddings.
- Apply **multi-hop attention networks** to refine phishing detection accuracy.

## References
1. Wu, J., et al. "Who Are the Phishers? Phishing Scam Detection on Ethereum via Network Embedding." *IEEE Transactions on Systems, Man, and Cybernetics: Systems*, 2020.
2. Ma, X., et al. "RiWalk: Fast Structural Node Embedding via Role Identification." *IEEE International Conference on Data Mining (ICDM)*, 2019.
3. Li, S., et al. "TGC: Transaction Graph Contrast Network for Ethereum Phishing Scam Detection." *ACSAC*, 2023.

## License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---
🚀 **Detect phishing addresses in Ethereum with high accuracy and efficiency!**
