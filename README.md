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
This research is centered on the development of a novel causal algorithm for detecting and quantifying extrinsic bias in Large Language Models (LLMs). Rather than treating bias as a surface-level lexical phenomenon or a correlational artifact, the proposed approach formalizes bias as an identifiable causal effect arising from sensitive attributes (e.g., race and gender) on model outputs.

The core objective is to design a language-agnostic causal metric based on structured counterfactual interventions in latent representation spaces, enabling statistically robust and semantically meaningful bias estimation across both natural language understanding (NLU) and generation (NLG) tasks.

Formally, bias is modeled as the Average Treatment Effect (ATE) of a sensitive attribute \( A \) on an output variable \( Y \), defined as:



$$
\[ \text{ATE} = \mathbb{E}[Y \mid do(A = a_1)] - \mathbb{E}[Y \mid do(A = a_0)] \]
$$

where the operator $$\( do(\cdot) \)$$ denotes a causal intervention that modifies the sensitive attribute while preserving all other relevant semantic factors. This formulation enables disentangling causal effects from spurious correlations, lexical artifacts, and dataset-specific biases.

The proposed algorithm performs controlled counterfactual interventions directly within the latent representation spaces of LLMs, rather than at the surface lexical level. This strategy allows the metric to remain invariant to language, vocabulary, and superficial syntactic variation, thereby enabling robust cross-linguistic and cross-domain generalization.

Portuguese is adopted as a primary experimental case study, not as a target language per se, but as a validation environment to assess the generalization, robustness, and stability of the proposed causal framework under linguistic and sociocultural shifts.

```text
phd_research/
│
├── 📂 literature/               # Theoretical foundation & Surveys
│
├── 📂 models/                   # Model catalog (Open Source vs Proprietary)
│
├── 📂 data/                     # Experimental datasets
│   
├── 📂 methodology/              # Causal formulation & Algorithms
│
├── 📂 experiments/              # Execution logs & Results
│
└── 📂 scripts/                  # Python scripts (Inference & Interventions)
```

Research Goals:

This PhD research aims to develop a novel causal algorithm for detecting and quantifying extrinsic bias in large language models (LLMs). The proposed approach formalizes bias as an identifiable causal effect, estimated through structured counterfactual interventions in latent representation spaces. The central objective is to design a language-agnostic causal metric capable of robustly measuring the impact of sensitive attributes on model behavior in both natural language understanding (NLU) and generation (NLG) tasks, with Portuguese serving as a primary experimental case study.

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

LinkedIn: https://linkedin.com/in/luislauriano/

CV: https://eltitolab.com/

Research Focus: Bias Mitigation, XAI, LLM Ethics.
