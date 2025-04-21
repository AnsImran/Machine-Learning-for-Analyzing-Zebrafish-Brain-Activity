# **Internship details start after the images.**

<img src="/figures/1.jpg" alt="1" width="1000"/>
<img src="/figures/2.jpg" alt="2" width="1000"/>
<img src="/figures/3.jpg" alt="3" width="1000"/>
<img src="/figures/l2l1__vs__norms_of_nrmse_vecs__and__percentage_of_explosions.jpg" alt="4" width="1000"/>



# 🧠 Machine Learning to Analyze Brain of Zebrafish

**👤 Author**: Ans Imran  
**🏛️ Lab**: Laboratoire Jean Perrin (LJP), Sorbonne Université  
**⏳ Duration**: 5 months & 5 days  
**🔬 Focus**: Machine Learning for Neural Data Analysis  

---

## 📌 Summary of Work

- 🛠️ Tuned the regularization parameter (λ) for compositional Restricted Boltzmann Machines (cRBMs) to improve training stability and reduce overfitting.
- 🧠 Used cRBMs to model functional connectivity in zebrafish brain data recorded from ~40,000 neurons.
- 📏 Evaluated models based on how well they reproduced brain activity statistics using nRMSE metrics.
- 📊 Analyzed connectivity patterns using PCA and K-means clustering.
- ✅ Built a pipeline to identify reliable (“good”) models based on performance thresholds.

---

## 🔍 Project Overview

### 1️⃣ Regularization Tuning

**🎯 Goal**: Find the right λ value for L2L1 regularization in cRBMs to avoid overfitting while keeping the model useful.

**🔧 What I Did**:
- Trained 600+ models across two λ ranges: `[0.005–0.1]` and `[0.5–5.0]`.
- Measured each model’s ability to reproduce 5 brain activity statistics.
- Defined “bad” models as those with nRMSE > 1.0 or NaN.
- Found λ = **0.09** to work best:
  - <10% bad models  
  - nRMSE norm ≤ 0.55

**💡 Concepts Used**:
- Hyperparameter tuning  
- L2L1 regularization  
- Model evaluation (custom metrics)  
- Train/test splitting

---

### 2️⃣ Functional Connectivity Analysis

**🎯 Goal**: Test if connectivity patterns stay consistent across models with different λ values.

**🔧 What I Did**:
- Generated coupling (connectivity) matrices from model weights.
- Flattened and projected them using PCA.
- Grouped them using K-means clustering.
- Found two clear clusters based on λ range, but structure of voxel connections was preserved.

**💡 Concepts Used**:
- PCA (dimensionality reduction)  
- K-means clustering  
- nRMSE for matrix similarity

---

### 3️⃣ Model Evaluation

**🎯 Goal**: Define a way to identify models that generalize well to unseen data.

**🔧 What I Did**:
- Used 4 of the 5 brain statistics to compute a 4D error vector per model.
- Calculated the L2 norm of this vector.
- Models with norms ≤ 0.55 were considered “good”.
- Confirmed results using visual tools like identity and polar plots.

**💡 Concepts Used**:
- Custom model scoring  
- Error thresholding  
- Diagnostic plotting

---

### 4️⃣ Tools and Workflow

| 🧩 Area             | ⚙️ Tools/Concepts Used                           |
|--------------------|--------------------------------------------------|
| Data Preparation   | Voxelization, z-score normalization              |
| Modeling           | cRBMs with L2L1 regularization                   |
| Evaluation & Viz   | nRMSE, heatmaps, polar plots, PCA, K-means      |
| Programming        | Python, Julia, NumPy, SciPy, scikit-learn, matplotlib   |
| Environment        | Jupyter Notebooks                                |

---

## ✅ Conclusion

- Regularization strength directly impacted both model quality and sparsity.
- λ in the range [0.05–0.1] produced the best results.
- Even lower-performing models showed similar connectivity structures.
- Functional relationships between brain voxels can be consistently captured by cRBMs.

---

## 🔄 Future Work

- Extend training to multiple zebrafish to test pattern consistency across individuals.

---

## 📎 Appendix

- 📄 Full Report: [Internship Report](Full Internship Report.pdf)
- 🧾 Code: *the code is private (property of Laboratoire Jean Perrin)*  
- 📊 Visuals: Included in the report (e.g., coupling matrices, PCA plots, nRMSE trends)
