Adaptive Liquid Time-Constant Networks for Multi-Regime Financial Forecasting

This repository implements a regime-aware, multi-asset financial forecasting framework that combines Liquid Time-Constant (LTC) networks, dynamic graph learning, and N-HiTS-style multi-horizon decoding.
The system is designed to handle non-stationarity, regime shifts, and evolving inter-asset correlations in financial time series.

📌 Key Features

Liquid Time-Constant Networks (LTC)
Continuous-time recurrent dynamics with asset-specific adaptation rates.

Dynamic Graph Neural Networks (GNN)
Learns time-varying inter-asset relationships instead of using static correlations.

Multi-Horizon Forecasting (N-HiTS-inspired)
Produces stable forecasts across multiple temporal resolutions.

Regime Awareness
Explicit regime detector (bull / bear / crisis) for adaptive behavior.

Strict Temporal Data Splits
Prevents information leakage by splitting data across historical market regimes.

Robust Regularization
Spectral normalization, gradient penalties, temporal smoothness, and forecast diversity losses.

Speed Optimized Training
Mixed-precision (AMP), batched LTC processing, pinned memory, and early stopping.

🏗️ Architecture Overview
Historical Prices
        ↓
Regime Detector
        ↓
Liquid Time-Constant Encoder (per asset)
        ↓
Dynamic Graph Structure Learning
        ↓
Graph Neural Network (Inter-asset reasoning)
        ↓
N-HiTS Multi-Scale Decoder
        ↓
Multi-Asset, Multi-Horizon Forecasts

📊 Visualizations & Evaluation

The repository includes a comprehensive visualization pipeline that generates:

Training Metrics Dashboard
Loss curves, log-scale trends, and overfitting analysis.

Time-Series Forecast Plots
Historical context + future predictions.

Detailed Multi-Asset Forecasts
Asset-wise MSE and MAE.

Forecast Error Heatmap
Error patterns across assets and time.

Rolling Performance Metrics
Stability and degradation analysis.

All figures are saved as high-resolution, publication-ready PNGs.

📁 Project Structure
├── model.py                  # LTC + GNN + N-HiTS hybrid model
├── train.py                  # Temporal training & evaluation pipeline
├── visualize.py              # Comprehensive evaluation & plotting suite
├── README.md
├── requirements.txt
└── outputs/
    ├── training_dashboard.png
    ├── time_series_forecasts.png
    ├── forecast_error_heatmap.png
    └── rolling_performance.png

🚀 Getting Started
1️⃣ Install Dependencies
pip install -r requirements.txt


Core dependencies:

PyTorch (≥ 2.0)

PyTorch Geometric

NCPS (Liquid Time-Constant Networks)

yfinance

NumPy, Pandas, Matplotlib, Seaborn

2️⃣ Run Training
python train.py


The training pipeline:

Downloads historical market data (Yahoo Finance)

Applies temporal regime-based splits

Trains with mixed precision and early stopping

Saves the best model checkpoint

3️⃣ Generate Visualizations
python visualize.py


This produces all evaluation figures automatically.

📈 Dataset

Assets: Equities, bonds, commodities, currencies

Period: 2000 – 2023

Frequency: Daily close prices

Normalization: Train-set statistics only (no leakage)

🧠 Design Philosophy

Robustness over raw accuracy
Conservative forecasts during uncertain regimes are treated as a feature, not a failure.

Graceful degradation
Performance deteriorates smoothly under unseen regimes instead of collapsing.

Financial realism
Temporal splits, regime awareness, and inter-asset dynamics reflect real trading conditions.

⚠️ Limitations

Uses price-only data (no fundamentals or macro variables)

Regime detector is heuristic and not externally labeled

Higher computational cost compared to classical models

🔮 Future Work

Multimodal inputs (news, macro indicators)

Causal graph discovery

Uncertainty estimation & prediction intervals

Portfolio optimization integration

Faster adaptation to unseen regimes (meta-learning)

📜 Citation

If you use this work, please cite:

Adaptive Liquid Time-Constant Networks with Dynamic Graph Learning
for Multi-Regime Financial Forecasting

📬 Contact

For questions, feedback, or collaboration, feel free to open an issue or reach out.

⭐ If you find this project useful, please consider starring the repository!
