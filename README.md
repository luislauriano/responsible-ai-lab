# Responsible AI Lab ⚖️🤖

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Python](https://img.shields.io/badge/Python-3.9%2B-blue)](https://www.python.org/)
[![Status](https://img.shields.io/badge/Status-Active%20Research-green)](https://github.com/)

**A central hub for research, development, and benchmarking in Fairness, Bias Mitigation, and Explainable AI (XAI).**

This repository serves as a living portfolio of my academic journey. It consolidates the source code, datasets, and literature review from my **Master's Thesis** (Data Balacing to Mitigate Bias) and establishes the framework for my **Ph.D. Research** (LLMs, Causal Fairness & Context-Specific Bias).

---

## 📂 Repository Overview

The repository is organized into two distinct research tracks:

### Part 1: 🎓 Master's (Completed)
**Focus:** *Data Balancing to Mitigate Sample and Algorithmic Bias: A Comparative Study*

This section contains the implementation of a large-scale study comparing how different data balancing techniques (SMOTE, Undersampling, Reweighting) impact the trade-off between **Model Performance** and **Fairness**.

```text
masters_research/
│
├── 📂 literature/               # 📚 References and Review
│
├── 📂 data/                     # Preprocessed datasets (e.g., German Credit)
├── 📂 notebooks/                # Jupyter Notebooks for experiments
│
├── 📂 src/                      # Helper functions (Reweighting wrappers)
└── 📂 results/                  # DALEX fairness plots and metrics
```

Key Highlights & Snippets:
🛡️ Fairness Audit with DALEX: Implementation of fairness_check() using the Four-Fifths Rule (80% rule) to visually detect bias.

⚖️ Reweighting Implementation: Practical example of Inverse Frequency Reweighting to mitigate bias without generating synthetic data.

```text
# Example of calculating sample weights for bias mitigation
from sklearn.utils.class_weight import compute_sample_weight

# Computing weights inversely proportional to class frequency
weights = compute_sample_weight(class_weight='balanced', y=y_train)

# Training a fairness-aware model
model.fit(X_train, y_train, sample_weight=weights)
```
📊 Trade-off Analysis: Notebooks demonstrating the impact of mitigation techniques on F1-Score vs. Equal Opportunity.

### 🔮 Part 2: Ph.D. Roadmap (LLMs)
Focus: Treating Bias in Large Language Models in Specific Contexts

This section hosts the roadmap and experimental framework for developing new metrics and benchmarks to detect representational and allocational bias in LLMs, with a focus on Causal Fairness

```text
phd_research/
│
├── 📂 literature/               # Theoretical foundation & Surveys
│
├── 📂 models/                   # Model catalog (Open Source vs Proprietary)
│
├── 📂 data/                     # Experimental datasets
│   ├── 📂 prompts/              # Bias detection prompts (EN/PT-BR)
│   └── experimental_sets/       # Curated datasets for benchmarking
│
├── 📂 methodology/              # Causal formulation & Algorithms
│
├── 📂 experiments/              # Execution logs & Results
│
└── 📂 scripts/                  # Python scripts (Inference & Interventions)
```

Research Goals:
Causal Analysis of Representational Bias: Investigate how sensitive attributes (e.g., race and gender) are encoded in the latent representation spaces of Large Language Models (LLMs), modeling representational bias as a causal effect within internal neural representations rather than as surface-level lexical correlations.

Causal Measurement of Allocational and Narrative Bias: Analyze how interventions on sensitive attributes causally influence LLM outputs in tasks of natural language understanding (NLU) and generation (NLG), particularly in the allocation of social roles, attribution of agency, and narrative framing, using controlled counterfactual interventions in the latent space.

Development of a Language-Agnostic Causal Metric: Design and validate a novel bias evaluation metric based on causal inference principles, capable of estimating the Average Treatment Effect (ATE) of sensitive attributes on model outputs, independent of language, with Portuguese as a primary experimental case study.

🚧 Content in this section is currently under active development.

### 🛠️ Tech Stack

```text
Language: Python 3.8+

Core Libraries: scikit-learn, pandas, numpy

Fairness & XAI: dalex (primary tool), fairlearn

Balancing: imbalanced-learn (SMOTE, NearMiss)
```

### 🤝 Contribution & Contact
I am open to discussions about AI Ethics, Algorithmic Fairness, and Research Collaborations.

Author: Luis Vinicius Lauriano de França

LinkedIn: https://www.linkedin.com/in/luislauriano/

CV: eltitolab.com

Research Focus: Bias Mitigation, XAI, LLM Ethics.
