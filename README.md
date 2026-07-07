# 🛡️ Bayesian Phishing Detection with Human-in-the-Loop (HITL)

> A Bayesian Machine Learning framework for phishing detection that combines **Bayesian Logistic Regression**, **uncertainty quantification**, and a **Human-in-the-Loop (HITL)** decision strategy.

<p align="center">
  <img src="https://raw.githubusercontent.com/gabrielcardoso-estatistico/BLR-HITL/refs/heads/main/evolucao.png" width="900">
</p>

---

## 📖 Overview

Traditional phishing detection systems generally produce deterministic predictions, forcing the model to classify every sample, even when uncertainty is high. This behavior often leads to **false positives**, blocking legitimate websites and reducing user trust.

This project proposes a **Bayesian inference framework** capable of estimating not only the probability of phishing but also the uncertainty associated with each prediction.

Instead of making uncertain decisions automatically, the framework delegates ambiguous cases to a human analyst, creating an adaptive **Human-in-the-Loop (HITL)** pipeline.

The approach provides:

- Bayesian probabilistic inference
- Uncertainty-aware predictions
- Probability calibration
- Human-assisted decision making
- Improved reliability in security-critical applications

---

# Framework

<p align="center">
  <img src="images/framework_hitl.png" width="900">
</p>

The workflow consists of four stages:

1. Feature extraction
2. Bayesian Logistic Regression
3. Uncertainty estimation
4. Human-in-the-Loop decision

---

# Bayesian Inference

Instead of estimating a single parameter value,

\[
P(y|x)
\]

the Bayesian model estimates the complete posterior distribution

\[
P(\theta|D)
\]

allowing uncertainty to be propagated into every prediction.

The predictive distribution is given by

\[
P(y^*|x^*,D)=\int P(y^*|x^*,\theta)P(\theta|D)d\theta
\]

This probabilistic formulation enables uncertainty-aware decision making.

---

# Human-in-the-Loop Decision Strategy

Rather than forcing the classifier to decide every sample, predictions are divided into three regions.

<p align="center">
  <img src="images/hitl_strategy.png" width="800">
</p>

| Prediction Probability | Decision |
|------------------------|----------|
| Low probability | Legitimate Website |
| High probability | Phishing Website |
| Intermediate probability | Human Analyst |

The uncertainty interval can be adjusted depending on the desired balance between automation and reliability.

---

# Results

## Model Calibration

<p align="center">
  <img src="images/calibration_curve.png" width="700">
</p>

The Bayesian model achieves excellent calibration.

- Expected Calibration Error (ECE): **0.0162**
- Reliable predictive probabilities
- Well-calibrated confidence estimates

---

## Reliability Improvement

When uncertain predictions are referred to a human analyst:

- Accuracy increases
- False positives decrease
- False negatives decrease
- Overall system reliability improves

<p align="center">
  <img src="images/results_table.png" width="900">
</p>

---

# Dataset

The experiments use a phishing website dataset containing engineered URL-based features, including:

- URL Length
- Number of Special Characters
- HTTPS usage
- Domain characteristics
- Shannon Entropy
- Structural URL features

Binary classification:

- Legitimate
- Phishing

---

# Technologies

- Python
- PyMC
- ArviZ
- Scikit-Learn
- NumPy
- Pandas
- Matplotlib
- Bayesian Logistic Regression
- MCMC Sampling

---

# Repository Structure

```
.
├── data/
├── images/
├── notebooks/
│   └── modelo_final.ipynb
├── models/
├── results/
├── README.md
```

---

# Main Contributions

✅ Bayesian phishing detection

✅ Predictive uncertainty estimation

✅ Probability calibration

✅ Human-in-the-Loop framework

✅ Adaptive decision threshold

✅ Security-oriented Bayesian inference

---

# Example Workflow

```text
URL
 │
 ▼
Feature Extraction
 │
 ▼
Bayesian Logistic Regression
 │
 ▼
Posterior Distribution
 │
 ▼
Probability + Uncertainty
 │
 ├──────────────┐
 ▼              ▼
Confident     Uncertain
Decision      Prediction
 │              │
 ▼              ▼
Automatic   Human Analyst
```

---

# Citation

If you use this project, please cite:

```bibtex
@article{bayesian_hitl_phishing,
  title={Bayesian Phishing Detection with Human-in-the-Loop Decision Framework},
  author={Gabriel Cardoso},
  year={2026}
}
```

---

# Future Work

- Active Learning integration
- Online Bayesian Updating
- Deep Bayesian Neural Networks
- Explainable AI (SHAP)
- Real-time browser extension
- Enterprise phishing detection pipeline

---

# License

MIT License
