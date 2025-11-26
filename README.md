# Crime Prediction with Temporal Validation
🇧🇷 *Versão em português disponível em [README_pt-BR.md](README_pt-BR.md)*

> **Note:** Source code and comments are in Portuguese (pt-BR) as this project addresses Brazilian public safety context and is intended for local stakeholders.

> Urban crime forecasting and classification system using machine learning with rigorous temporal validation to prevent data leakage

Integrated crime prediction system with two complementary modules:

1. **Volume Forecasting (Regression)**: Predicts daily crime counts by location using Random Forest Regressor
2. **Crime Type Classification**: Probabilistic multi-class prediction using Random Forest and XGBoost

**Key Features:**
- ✅ Temporal K-Fold validation with expanding windows (prevents data leakage)
- ✅ Out-of-time testing on 9 months of future data (Jan-Sep 2025)
- ✅ Automated drift monitoring system
- ✅ Production-ready models with complete reproducibility

## 🎯 Results

| Module | Model | Metric | Performance |
|--------|-------|--------|-------------|
| Volume Prediction | Random Forest | MAE | 0.52 crimes/day |
| Volume Prediction | Random Forest | R² | 0.655 |
| Crime Classification | XGBoost | F1-Score | 0.903 |
| Crime Classification | XGBoost | Accuracy | 90.0% |

**Case Study:** 75,029 criminal records from Espírito Santo, Brazil (2024-2025)

## 🔬 Methodology Highlights

- Temporal validation with 3-fold cross-validation (no future data leakage)
- Grid search optimization (81, 54, and 18 hyperparameter combinations)
- Spatial feature engineering (100 geographic regions)
- Temporal lag features (1, 7, 30 days + 7-day moving average)
- Performance monitoring with drift detection thresholds

## 📂 Repository Structure

```
crime-prediction-temporal-validation/
│
├── data/
│   ├── raw/                    # Complete dataset from 2024 to Sep/2025
│   └── future/                 # Monthly datasets for 2025 (Jan-Sep)
│
├── predictions/
│   ├── volume/                 # Volume prediction outputs (CSV)
│   └── classification/         # Crime type classification outputs (CSV)
│
├── results/
│   ├── figures/                # Generated plots and visualizations
│   └── screenshots/            # Training/evaluation output screenshots
│
├── notebooks/                  # Jupyter notebooks for analysis
├── requirements.txt
├── README_pt-BR.md
└── README.md
```

### 📝 Directory Descriptions

- **`data/raw/`**: Original unprocessed crime records from Espírito Santo public database
- **`data/future/`**: Monthly crime data files used for out-of-time validation (2025)
- **`predictions/volume/`**: Daily crime volume forecasts per location
- **`predictions/classification/`**: Crime type predictions with probabilities
- **`results/figures/`**: Performance charts, drift monitoring plots, and visualizations
- **`results/screenshots/`**: Console outputs and training logs
- **`notebooks/`**: Exploratory data analysis, model training, and evaluation notebooks

> **Note:** The `data/` directory is not included in the repository due to privacy considerations. Please refer to the official Espírito Santo public safety database for dataset access.

## 🚀 Quick Start

```bash
# Clone repository
git clone https://github.com/raphaeldallorto/crime-prediction-temporal-validation.git
cd crime-prediction-temporal-validation

# Install dependencies
pip install -r requirements.txt
```

## 📄 Citation

If you use this work, please cite:

```bibtex
@mastersthesis{dallorto2025crime,
  title={Urban Crime Volume Prediction and Classification Using Random Forest and XGBoost: A Temporal Validation Approach},
  author={Dall'Orto, Raphael Lugon Campo},
  year={2025},
  school={Federal University of Espírito Santo}
}
```

## 👤 Author

**Raphael Lugon Campo Dall'Orto**
- GitHub: [@raphaeldallorto](https://github.com/raphaeldallorto)

## 📜 License

This project is licensed under the MIT License - see [LICENSE](LICENSE) file for details.
