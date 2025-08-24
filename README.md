# Chemistry_ML
Mini-project: Predicting HOMO–LUMO gap using Machine Learning

---

## 🎯 Goal
The **HOMO–LUMO gap** is an important electronic property of molecules that influences:  
- Optical absorption  
- Reactivity  
- Conductivity  

We attempt to predict the HOMO–LUMO gap using molecular descriptors.  

---

## 📊 Dataset
- **Source**: Subset inspired by QM9 (5,000 molecules).  
- **Features**:  
  - HOMO energy (eV)  
  - LUMO energy (eV)  
  - Dipole moment, μ (Debye)  
  - Polarizability, α (Bohr³)  
- **Target**: HOMO–LUMO gap (eV)  

---

## 🔧 Methods
We trained three regression models:  
1. **Linear Regression**  
2. **Random Forest Regressor**  
3. **LASSO Regression (feature selection)**  

---

## 📈 Results
- **Linear Regression (with HOMO & LUMO)** → R² = **1.0** (perfect, since gap = LUMO – HOMO).  
- **Random Forest** → R² ≈ **0.99**.  
- **LASSO (without LUMO)** → R² ≈ **0.001**, showing that HOMO is weakly predictive, while μ and α contribute little.  

---

## 🔍 Insights
- If **both HOMO & LUMO are included**, predicting GAP is trivial.  
- When **excluding LUMO**, the model struggles, highlighting the importance of **descriptor choice**.  
- HOMO energy shows the strongest correlation with the gap, consistent with chemical intuition.  

---

## 📌 Next Steps
- Add more molecular descriptors (size, weight, RDKit features).  
- Try more advanced ML models (Gradient Boosting, SVR, Neural Nets).  
- Extend project to other molecular properties (dipole moment, adsorption energies).  

---

## ⚙️ Requirements
Install dependencies with:
```bash
pip install -r requirements.txt
