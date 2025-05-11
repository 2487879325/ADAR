# ADAR: Adaptive Dynamic Attribute and Rule Management Framework

> A fuzzy inference system for high-dimensional data—integrating dual weighting, rule growth & pruning, and attribute selection

---

## 1. Project Overview

ADAR (Adaptive Dynamic Attribute and Rule) is a framework designed to address the challenges of high-dimensional data in neuro-fuzzy inference systems. It introduces learnable weighting mechanisms for both fuzzy rules and input attributes, combined with automated strategies for rule growth and pruning, as well as attribute pruning. This dynamic management simplifies model structures, suppresses noise, enhances prediction accuracy, and maintains interpretability.

Key features:
- **Dual Weighting Mechanism**: Differentiable weights for both fuzzy rules and input attributes, updated via backpropagation with L1 regularization.
- **Adaptive Rule Management**: Automatic growth of new rules when validation error plateaus, and pruning of low-importance rules based on a rule-pruning threshold.
- **Attribute Pruning**: Periodic removal of attributes whose learned importance falls below a defined threshold, reducing dimensionality and noise.
- **Integration with ANFIS & SOFENN**: Seamless application to both static ANFIS and incremental SOFENN architectures.
- **Scalable Performance**: Demonstrated to outperform state-of-the-art baselines in RMSE and model explainability across four benchmark datasets.

---

## 2. Repository Structure

```
ADAR/
├── ADAR_dataset_demo.ipynb   # Core Jupyter notebook: implementation details, experiments, and visualizations
├── config.yaml               # Sample configuration file
├── requirements.txt          # Dependency list
└── LICENSE                   # Open-source license (MIT)
```

---

## 3. Setup

1. **Clone the repository**  
   ```bash
   git clone https://github.com/RyanLiu1999/ADAR.git
   cd ADAR
   ```

2. **Create a virtual environment and install dependencies**  
   ```bash
   python3 -m venv venv
   source venv/bin/activate   # macOS/Linux
   # venv\Scripts\activate  # Windows
   pip install -r requirements.txt
   ```

---

## 4. Quick Start

1. **Launch Jupyter Notebook**  
   ```bash
   jupyter notebook
   ```
2. **Open and run**  
   - Open `ADAR_dataset_demo.ipynb`  
   - Execute cells in sequence to load data, train ADAR-ANFIS or ADAR-SOFENN, evaluate results, and view visualizations.

---

## 5. Core Modules

| Module               | Description                                                               |
|----------------------|---------------------------------------------------------------------------|
| Data Loader          | Support for Auto MPG, Beijing PM2.5, Boston Housing, Appliances Energy    |
| Models               | Implementations of ADAR-ANFIS, ADAR-SOFENN, and baseline fuzzy/ML models |
| Training             | Backpropagation with dual weighting, L1 regularization, RG&P strategy     |
| Prune/Grow           | Rule Growing & Pruning (RG&P) and Attribute Pruning (AP) mechanisms       |
| Metrics              | RMSE, overlap index (I<sub>ov</sub>), fuzzy set position index (I<sub>fsp</sub>) |
| Rule Extraction      | Export human-readable fuzzy IF–THEN rules                                 |

---

## 6. Hyperparameters

| Parameter                                           | Description                                                                                  | Default                |
|-----------------------------------------------------|----------------------------------------------------------------------------------------------|------------------------|
| `learning_rate`                                     | Optimizer learning rate                                                                      | 0.01                   |
| `batch_size`                                        | Batch size for training                                                                      | 512                    |
| `epochs`                                            | Number of training epochs                                                                    | 1500                   |
| `max_rules`                                         | Maximum number of fuzzy rules (model capacity)                                               | e.g., 3, 5, 7, 9       |
| `attribute_pruning_threshold` (`θattr`)             | Importance weight threshold below which attributes are pruned                                 | 0.1                    |
| `attribute_pruning_frequency` (`PA_Freq`)           | Number of epochs between attribute pruning evaluations                                        | 25                     |
| `rule_pruning_threshold` (`θr`)                     | Importance weight threshold below which rules are pruned                                      | 0.1                    |
| `rule_pruning_frequency` (`PR_Freq`)                | Number of epochs between rule pruning evaluations                                             | 50                     |
| `growth_sensitivity_threshold` (`G_Thres`)          | Minimum validation error improvement required to avoid triggering rule growth                  | 5e-5                   |

---

## 7. Experimental Results & Visualization

Refer to the notebook for benchmark results on four datasets, including RMSE comparisons, rule count dynamics, overlap index and fuzzy set positioning analyses.

---

## 8. Citation

Please cite our work if you use ADAR:

> @article{liu2025dynamic,
  title={A Dynamic Fuzzy Rule and Attribute Management Framework for Fuzzy Inference Systems in High-Dimensional Data},
  author={Liu, Ke and Ma, Jing and Lai, Edmund MK},
  journal={arXiv preprint arXiv:2504.19148},
  year={2025}
}
---

## 9. License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

---

## 10. Contact

For questions or collaboration, please contact:  
**Jing Ma** ✉️ jing.ma@aut.ac.nz
