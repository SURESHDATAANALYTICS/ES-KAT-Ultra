# ES-KAT Ultra: Component Kernel Attention Transformer for Early Sepsis Prediction

This repository hosts the code for **ES-KAT Ultra**, a parameter-efficient Feature-Tokenized Transformer with Component Kernel Attention for 12-hour sepsis prediction in the ICU, validated on MIMIC-IV v3.1.

> **Status:** Under peer review at *Medical & Biological Engineering & Computing* (Springer Nature). Full implementation will be released upon manuscript acceptance.

## Paper

**Title:** Pathophysiology-Grounded Feature Engineering for Early Sepsis Prediction in the ICU: A Comprehensive Evaluation of an FT-Transformer with Component Kernel Attention on MIMIC-IV

**Authors:** Suresh Rajendran, Santhi Krishnan

**Affiliation:** School of Computer Science and Engineering, Vellore Institute of Technology, Vellore, India

**Status:** Under peer review (submitted May 2026)

## Key Results

- **AUROC** at 12-hour prediction horizon: **0.9327 ± 0.0026** (5-fold nested cross-validation)
- **AUROC** at 6-hour: 0.9394 ± 0.0022; **3-hour:** 0.9436 ± 0.0016
- **AUPRC** at 12-hour: 0.1623 ± 0.0089 (17.6× random baseline at 0.92% prevalence)
- **Patient-level AUROC:** 0.9389 ± 0.0007 across 5 outer test folds (63,487 patients aggregated)
- Outperformed LSTM by +0.017 AUROC with 42% fewer parameters
- Validated on 63,487 MIMIC-IV patients (5,749,991 hourly observations)

## Methodology Highlights

- **Pathophysiology-grounded feature engineering** across five organ-system pillars
- **Ensemble feature selection** using 8 methods with balanced allocation constraint
- **Component Kernel Attention** combining Tanh, ReLU, GELU kernels with learned mixing weights
- **Nested 5-fold cross-validation** at natural prevalence (no SMOTE, no class balancing)
- **10-innovation systematic ablation** revealing feature engineering > architecture
- **Three deployment-ready operating points** with calibrated probabilities

## Repository Contents

This repository will be populated with full source code upon manuscript acceptance:

```
ES-KAT-Ultra/
├── src/
│   ├── preprocessing/    # MIMIC-IV cohort construction
│   ├── features/         # 8-method ensemble feature selection
│   ├── models/           # ES-KAT Ultra architecture + CKA layer
│   ├── training/         # Nested CV training pipeline
│   └── evaluation/       # 14-metric evaluation framework
├── configs/              # Hyperparameter configurations
├── notebooks/            # Reproducibility notebooks
├── docs/                 # Methodology documentation
├── requirements.txt
├── LICENSE
└── README.md
```

## Data Access

This work uses **MIMIC-IV v3.1**, available through PhysioNet:

https://physionet.org/content/mimiciv/3.1/

Access requires PhysioNet credentialing and completion of CITI Program training.

## Citation

If you use this work, please cite (citation will be updated upon acceptance):

```bibtex
@article{rajendran2026eskat,
  title   = {Pathophysiology-Grounded Feature Engineering for Early Sepsis Prediction in the ICU: A Comprehensive Evaluation of an FT-Transformer with Component Kernel Attention on MIMIC-IV},
  author  = {Rajendran, Suresh and Krishnan, Santhi},
  journal = {Medical \& Biological Engineering \& Computing},
  year    = {2026},
  note    = {Under peer review}
}
```

## License

MIT License (see [LICENSE](LICENSE)).

## Contact

**Corresponding author:** Santhi Krishnan — santhikrishnan@vit.ac.in

**First author:** Suresh Rajendran — suresh.r2023@vitstudent.ac.in

---

*Last updated: May 2026 (initial commit; full code release pending manuscript acceptance)*
