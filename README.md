# Machine-Learning-for-Analyzing-Zebrafish-Brain-Activity

## This repository contains a record of the work I completed during my internship at the Laboratoire Jean Perrin, Sorbonne Université (Université Paris 6).



# 🧠 Machine Learning to Analyze Brain of Zebrafish

> This repository summarizes my internship work at **Laboratoire Jean Perrin, Sorbonne Université**, where I applied machine learning techniques — specifically, **compositional Restricted Boltzmann Machines (cRBMs)** — to analyze neural activity in zebrafish.

---

## 🚀 Summary

- 🧬 **Project Focus**: Functional connectivity modeling in zebrafish larvae brain using cRBMs.
- 🧠 **Data**: Whole-brain calcium imaging data (SPIM-based), ~40,000 neurons, voxel-averaged activity.
- 🤖 **ML Approach**: Compositional Restricted Boltzmann Machines with **L2L1 regularization**.
- 📈 **Optimization**: Hyperparameter search for regularization strength (λ) to balance underfitting/overfitting.
- 🔄 **Generative Modeling**: cRBMs learned hidden assemblies and generated statistically similar neural activity.
- 📊 **Analysis**: PCA, K-means clustering, RMSE metrics, and functional connectivity comparisons.
- 🧩 **Key Finding**: Functional connectivity matrices are consistent across models — robust to model imperfections.
- 💡 **Tools Used**: Python, NumPy, scikit-learn, matplotlib, PCA, k-means, identity plots, heatmaps.

---

## 📂 Project Breakdown

### 1. **Scientific Context**
- **Goal**: Extract interpretable neural assemblies and functional connections from large-scale zebrafish brain recordings.
- **Why ML?**: Manual/heuristic methods fail at whole-brain scale; generative models (cRBMs) offer interpretable, scalable alternatives.

### 2. **Model Architecture**
- **cRBMs**: Probabilistic generative models with visible units (voxels) and hidden units (assemblies).
- **Regularization**: Employed custom **L2L1** regularization for controlled sparsity.
- **Training**: Models trained on individual fish using z-scored voxel activity.

### 3. **Hyperparameter Optimization**
- **Main Task**: Tune λ (L2L1 regularization) to:
  - Reduce overfitting
  - Minimize bad models (nRMSE > 1 or NaN)
  - Reproduce key statistics of brain activity
- **Evaluation Metrics**:
  - Mean voxel activity ⟨v⟩, hidden unit activity ⟨h⟩
  - Pairwise interactions: ⟨vv⟩, ⟨vh⟩, ⟨hh⟩
  - **nRMSE** scores used to assess model fidelity

### 4. **Functional Connectivity Analysis**
- **Coupling Matrix**: Computed from learned weights; reflects voxel-to-voxel interaction strength.
- **Consistency Check**:
  - Models with different λ produce similar coupling matrices
  - Matrix structure is stable across cRBMs — even “bad” models
- **Dimensionality Reduction**: PCA showed two clear matrix clusters (based on λ range).
- **Clustering**: K-means validated that matrix structure stems from regularization-induced sparsity.

### 5. **Key Results**
- ✅ **Optimal λ ≈ 0.09**: Best balance between model accuracy and sparsity.
- 📉 **< 10% bad cRBMs** in optimal λ range.
- 🔁 **Cross-model similarity**: Functional connectivity matrix conserved across cRBMs.
- 🧠 **Inference**: Robust voxel assemblies exist and are identifiable despite neuron-level noise.

---

## 🛠️ Technical Skills Demonstrated

| Skill                             | Description |
|----------------------------------|-------------|
| **Unsupervised Learning**        | Training generative models (cRBMs) on high-dimensional time-series brain data |
| **Hyperparameter Optimization**  | Grid search over λ, error analysis using nRMSE |
| **Model Evaluation**             | Identity plots, custom nRMSE metrics, failure analysis |
| **Statistical Analysis**         | PCA, clustering (k-means), histogram comparisons |
| **Data Engineering**             | Voxel-based preprocessing of zebrafish brain imaging data |
| **Visualization**                | Heatmaps, PCA plots, polar plots, identity plots |
| **Scientific Communication**     | Generated interpretive figures and built reproducible analysis pipelines |

---

## 📌 What's Next?

- Train cross-subject cRBMs to explore **shared neural assemblies** across multiple zebrafish.
- Investigate how **functional connectivity maps** relate to **structural connectivity**.
- Extend findings to other datasets and brain models.

---

## 📚 Reference

The project is based on and extends findings from:  
🧾 [van der Plas et al. (2023), eLife](https://doi.org/10.7554/eLife.83139)

