# ADAR: Adaptive Dynamic Attribute and Rule Management Framework

> A Dynamic Fuzzy Rule and Attribute Management Framework for Fuzzy Inference Systems in High-Dimensional Data
> Ke Liu, Jing Ma (✉️ jing.ma@aut.ac.nz), Edmund M-K Lai

---

## Project Overview

This repository contains the Jupyter Notebook `ADAR_数据集测试.ipynb`, which implements the **ADAR** (Adaptive Dynamic Attribute and Rule) framework. This framework is designed for dynamically managing fuzzy rules and input attributes in high-dimensional datasets. By combining attribute- and rule-level weighting with automated growth and pruning strategies, ADAR simplifies model structure without sacrificing performance or interpretability. The notebook includes benchmark experiments demonstrating the framework's accuracy and ability to reduce rule complexity compared to baseline methods.

---

## Repository Structure

It is recommended to structure your repository as follows if you plan to share this work:

.
├── ADAR_数据集测试.ipynb       # The main Jupyter Notebook with implementations and experiments
├── README.txt              # This file (or README.md)
├── LICENSE                 # Your chosen license file (e.g., MIT)
└── requirements.txt        # Python dependencies

The notebook fetches datasets directly or uses pre-loaded datasets from libraries like scikit-learn.

---

## Installation

1.  **Clone the repository (if you create one):**
    ```bash
    git clone [https://github.com/your-username/adar-framework.git](https://github.com/your-username/adar-framework.git)
    cd adar-framework
    ```
2.  **Create a virtual environment and install dependencies:**
    ```bash
    python3 -m venv venv
    source venv/bin/activate      # Linux/macOS
    # venv\Scripts\activate.bat  # Windows
    pip install -r requirements.txt
    ```

---

## How to Use the Notebook (`ADAR_数据集测试.ipynb`)

1.  **Environment:** Ensure you have a Jupyter Notebook or JupyterLab environment installed.
2.  **Open and Run:**
    * Open the `ADAR_数据集测试.ipynb` file in your Jupyter environment.
    * Execute the cells sequentially.
3.  **Content:**
    * **Data Loading:** The notebook loads various datasets (e.g., Boston Housing, YearPredictionMSD, Auto MPG, Appliances Energy) either by fetching them from online repositories (like UCI) or using scikit-learn's dataset loaders.
    * **Model Definitions:** It contains Python classes for ADAR-ANFIS, ADAR-SOFENN, and other baseline models (standard ANFIS, SOFENN, FuBiNFS, RVFL). These classes include the core logic for fuzzy layers, attention mechanisms, rule/attribute management (growth and pruning).
    * **Training:** Functions like `train_attention_dynamic_attribute_and_rule_sofenn` and `train_attention_dynamic_attribute_and_rule_anfis` handle the model training process. This includes data scaling, optimization, and the dynamic adjustments of rules and attributes.
    * **Evaluation:** After training, models are evaluated using metrics like RMSE, Average Overlap Index ($I_{ov}$), and Average Fuzzy Set Position Index ($I_{fsp}$).
    * **Rule Extraction:** Methods are provided to extract human-readable fuzzy rules from the trained ADAR models.
    * **Experiments:** The notebook is structured to run experiments across different datasets and model configurations, often involving multiple repeats for robustness. Results, including performance metrics and extracted rules, are typically printed in the cell outputs. Plots may also be generated to visualize training progress or results.

---

## Key Parameters (configurable within the notebook)

The behavior of the ADAR models within the notebook can be configured by changing parameters directly in the Python code, typically within the experiment setup cells or function calls. Key parameters include:

* `initial_n_rules` or `n_rules`: The starting or maximum number of fuzzy rules.
* `learning_rate` (`lr`): The learning rate for the optimizer.
* `epochs`: The number of training epochs.
* `batch_size`: The number of samples per training batch.
* `prune_threshold` (for attributes and rules, e.g., `theta_attr`, `theta_rule`): Thresholds below which attributes or rules are considered for pruning.
* `prune_frequency` (e.g., `pa_freq`, `pr_freq`): How often (in epochs) pruning checks are performed.
* `grow_threshold` or `growth_thres`: Sensitivity threshold for triggering new rule growth.
* `lambda_attention`, `lambda_rule_attention`, `lambda_diversity`: Regularization coefficients for attention and diversity losses.

Refer to the specific function calls (e.g., `train_attention_dynamic_attribute_and_rule_sofenn`, `train_attention_dynamic_attribute_and_rule_anfis`, and other model training functions) in the notebook for how these are set.

---

## Evaluation Metrics

The notebook evaluates models using the following metrics, with calculations performed directly within the Python code:

* **RMSE**: Root Mean Square Error for prediction accuracy.
* **Iov (Overlap Index)**: Measures rule overlap. A lower value indicates better rule distinguishability.
* **Ifsp (Fuzzy Set Position Index)**: Evaluates membership function distribution and coverage. A lower value suggests more accurate positioning.

Experiment scripts and cells within the notebook will output these results, often to `results_...` subdirectories (if created by the code, e.g., `results_sofenn`, `results_anfis`) or directly in the notebook output.

---

## `requirements.txt`

Based on the imports in `ADAR_数据集测试.ipynb`, your `requirements.txt` file should include:

numpy
pandas
torch
scikit-learn
matplotlib
seaborn
scipy
scikit-fuzzy
ucimlrepo
tqdm


---

## Citation

If you use this work, please cite the original paper:

```bibtex
@article{liu2024dynamic,
  title={A Dynamic Fuzzy Rule and Attribute Management Framework for Fuzzy Inference Systems in High-Dimensional Data},
  author={Liu, Ke and Ma, Jing and Lai, Edmund M-K},
  journal={arXiv preprint arXiv:xxxx.xxxxx}, % Please update with actual arXiv ID or publication venue
  year={2024} % Please update with actual publication year
}
(The provided PDF is likely a preprint. Please update the citation with the correct arXiv ID, publication details, and year once formally published. The PDF itself does not specify an arXiv ID or a 2025 publication year for the preprint.)

License
This project is licensed under the MIT License. You would need to create a LICENSE file with the MIT License text if you choose this license.

Contact
Corresponding author: Jing Ma (✉️ jing.ma@aut.ac.nz)
