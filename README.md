# ADAR: Adaptive Dynamic Attribute and Rule Management Framework

> A fuzzy inference system for high-dimensional data—integrating dynamic weighting, growth, and pruning of attributes and rules

---

## 1. Project Overview

ADAR (Adaptive Dynamic Attribute and Rule) is a framework for fuzzy inference systems on high-dimensional data. By introducing attention mechanisms at both the attribute and rule levels, combined with automatic growth and pruning strategies, ADAR dynamically manages input attributes and fuzzy rules to simplify model structures, enhance prediction accuracy, and maintain interpretability.

Key features:
- **Attribute and Rule Weighting**: Assign dynamic weights to different input attributes and fuzzy rules.
- **Automatic Growth**: Dynamically add fuzzy rules based on sensitivity thresholds.
- **Automatic Pruning**: Remove redundant or low-contribution attributes/rules based on thresholds and frequency.
- **Visualization & Interpretability**: Extract and present human-readable fuzzy rules.

---

## 2. Repository Structure

```
ADAR/
├── ADAR_dataset_demo.ipynb   # Core Jupyter notebook: implementation details, experiments, and visualization
├── config.yaml              # Sample configuration file
├── requirements.txt         # Dependency list
└── LICENSE                  # Open-source license (MIT)
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
   - Execute cells in order to observe data loading, model training, evaluation results, and visualizations.

---

## 5. Core Modules

| Module               | Description                                                               |
|----------------------|---------------------------------------------------------------------------|
| Data Loader          | Support for Boston Housing, YearPredictionMSD, Auto MPG, and more datasets|
| Models               | Implementations of ADAR-ANFIS, ADAR-SOFENN, and various baseline models   |
| Training             | Dynamic adjustment of attribute/rule weights, model optimization, logging |
| Prune/Grow           | Automatic addition or removal of rules/attributes based on thresholds     |
| Metrics              | RMSE, overlap index $I_{ov}$, fuzzy set position index $I_{fsp}$         |
| Rule Extraction      | Export human-readable fuzzy rules                                         |

---

## 6. Configuration Parameters

| Parameter              | Description                                | Example Default |
|------------------------|--------------------------------------------|-----------------|
| `initial_n_rules`      | Initial number of fuzzy rules              | 10              |
| `learning_rate` (`lr`) | Learning rate for the optimizer            | 0.01            |
| `epochs`               | Number of training epochs                  | 100             |
| `batch_size`           | Batch size                                 | 32              |
| `theta_attr` / `theta_rule` | Pruning thresholds for attributes/rules | 0.001           |
| `pa_freq` / `pr_freq`  | Pruning check frequency (in epochs)        | 10              |
| `growth_thres`         | Growth threshold for new rules             | 0.05            |
| `lambda_attention`     | Regularization coefficient for attention   | 0.1             |
| `lambda_diversity`     | Regularization coefficient for diversity   | 0.01            |

---

## 7. Experimental Results & Visualization

- Comparative experiments on different datasets demonstrate that ADAR significantly reduces the number of fuzzy rules while maintaining or improving prediction accuracy.
- The notebook includes loss curves, RMSE comparison bar charts, and overlap index variation plots.

---

## 8. Citation

If you use this framework in research or production, please cite:

> Liu, K., Ma, J., & Lai, E. M.-K. (2024). A Dynamic Fuzzy Rule and Attribute Management Framework for Fuzzy Inference Systems in High-Dimensional Data. *arXiv preprint arXiv:xxxx.xxxxx*.

---

## 9. License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

---

## 10. Contact

For questions or collaboration, please contact:  
**Jing Ma** ✉️ jing.ma@aut.ac.nz
