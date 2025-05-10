# ADAR: Adaptive Dynamic Attribute and Rule Management Framework

> A Dynamic Fuzzy Rule and Attribute Management Framework for Fuzzy Inference Systems in High-Dimensional Data  
> Ke Liu, Jing Ma (✉️ jing.ma@aut.ac.nz), Edmund M-K Lai  


---

## Project Overview

This repository contains the implementation of the **ADAR** (Adaptive Dynamic Attribute and Rule) framework for dynamically managing fuzzy rules and input attributes in high-dimensional datasets. By combining attribute- and rule-level weighting with automated growth and pruning strategies, ADAR simplifies model structure without sacrificing performance or interpretability. Benchmark experiments demonstrate superior accuracy and reduced rule complexity compared to baseline methods.

---

## Repository Structure

```
.
├── README.txt              # This file
├── LICENSE                 # MIT License
├── requirements.txt        # Python dependencies
│
├── data/                   # Example datasets or download scripts
│   ├── auto_mpg.csv
│   ├── beijing_pm25.csv
│   ├── boston_housing.csv
│   └── appliances_energy.csv
│
├── src/                    # Core implementation
│   ├── adar_anifis.py      # ADAR with ANFIS implementation and CLI
│   ├── adar_sofenn.py      # ADAR with SOFENN implementation and CLI
│   └── utils.py            # Data loading, evaluation metrics (RMSE, Iov, Ifsp), etc.
│
├── experiments/            # Experiment scripts and config
│   ├── run_all.py          # Reproduce all baseline comparisons
│   └── config.yaml         # Experiment settings
│
└── notebooks/              # Jupyter notebooks for analysis and visualization
    └── analysis.ipynb      # Results visualization and ablation study
```

---

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/adar-framework.git
   cd adar-framework
   ```
2. Create a virtual environment and install dependencies:
   ```bash
   python3 -m venv venv
   source venv/bin/activate      # Linux/macOS
   venv\Scripts\activate.bat   # Windows
   pip install -r requirements.txt
   ```

---

## Quick Start

### Train ADAR-ANFIS
```bash
python src/adar_anifis.py \
  --dataset data/auto_mpg.csv \
  --max_rules 9 \
  --theta_attr 0.1 \
  --pa_freq 25 \
  --theta_rule 0.1 \
  --pr_freq 50 \
  --growth_thres 5e-5 \
  --output results/anifis_auto_mpg/
```

### Train ADAR-SOFENN
```bash
python src/adar_sofenn.py \
  --dataset data/beijing_pm25.csv \
  --max_rules 7 \
  --theta_attr 0.1 \
  --pa_freq 25 \
  --theta_rule 0.1 \
  --pr_freq 50 \
  --growth_thres 5e-5 \
  --output results/sofenn_pm25/
```

### Reproduce All Experiments
```bash
python experiments/run_all.py --config experiments/config.yaml
```

---

## Parameters

| Parameter        | Description                                              | Default |
| ---------------- | -------------------------------------------------------- | ------- |
| `--max_rules`    | Maximum number of fuzzy rules                            | `9`     |
| `--theta_attr`   | Attribute pruning threshold (θ_attr)                     | `0.1`   |
| `--pa_freq`      | Attribute pruning frequency (epochs)                     | `25`    |
| `--theta_rule`   | Rule pruning threshold (θ_r)                             | `0.1`   |
| `--pr_freq`      | Rule pruning frequency (epochs)                          | `50`    |
| `--growth_thres` | New rule growth sensitivity (G_thresh)                   | `5e-5`  |

---

## Evaluation Metrics

- **RMSE**: Root Mean Square Error for prediction accuracy.
- **Iov (Overlap Index)**: Measures rule overlap.
- **Ifsp (Fuzzy Set Position Index)**: Evaluates membership function distribution.

All metrics are implemented in `src/utils.py`. Experiment scripts save results (CSV and plots) to the `results/` directory.

---

## Citation

Please cite this work as:

```bibtex
@article{liu2025dynamic,
  title={A Dynamic Fuzzy Rule and Attribute Management Framework for Fuzzy Inference Systems in High-Dimensional Data},
  author={Liu, Ke and Ma, Jing and Lai, Edmund MK},
  journal={arXiv preprint arXiv:2504.19148},
  year={2025}
}
```

---

## License

This project is licensed under the **MIT License**. See [LICENSE](LICENSE) for details.

---

## Contact

**Corresponding author**: Jing Ma (✉️ jing.ma@aut.ac.nz)
