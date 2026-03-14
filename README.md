# otdr-ml-final
Reproducible OTDR ML pipeline: synthetic OTDR-like dataset generation, feature engineering, multi-family classification (LogReg + Random Forest), evaluation, and saved artifacts. Includes Binder link for click-to-run reproducibility.


# OTDR ML Final Project (Reproducible)

This repository contains a reproducible Machine Learning (ML) pipeline for classifying OTDR-like traces into four actionable condition classes:

- **Class 0:** Normal / Baseline  
- **Class 1:** Reflective Event (connector/mechanical-like spikes)  
- **Class 2:** Loss Event (step loss / increased attenuation)  
- **Class 3:** Major Fault (break/end-of-fiber-like termination)

The pipeline is designed as a proof-of-concept using **synthetic OTDR-like data** so results can be reproduced by anyone.

---

## Quick Start (Recommended)

### Run in your browser (Binder)
Click the link below to launch and run the notebook without installing anything:

**Binder:** https://jupyter.org/try-jupyter/lab/index.html?path=otdr_ml_pipeline.ipynb

Optional badge:

[![Open in Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/imccommons/otdr-ml-final/HEAD?labpath=otdr_ml_pipeline.ipynb)

---

## Run Locally

### Requirements
- Python 3.10+ recommended
- Packages listed in `requirements.txt`

### Steps
1. Install dependencies:
   ```bash
   pip install -r requirements.txt

2.  Start Jupyter:

     Jupyter Notebook
     
4.  Open and run:
    
    -   `otdr_ml_pipeline.ipynb`
        
    -   Use **Kernel → Restart & Run All** to reproduce results
        

----------

## What the Notebook Does

1.  **Generates dataset**
    
    -   Synthetic OTDR-like traces (≥ 5,000 records)
        
2.  **Feature engineering (≥ 10 features)**
    
    -   Slope/trend features
        
    -   Peak/spike features (reflective events)
        
    -   Step-loss features (loss events)
        
    -   Termination/failure features (major faults)
        
    -   Plus basic metadata features
        
3.  **Trains multi-family models**
    
    -   Logistic Regression (interpretable baseline)
        
    -   Random Forest (nonlinear classical ML)
        
4.  **Evaluates performance**
    
    -   Macro-F1 and per-class precision/recall/F1
        
    -   Confusion matrices
        
5.  **Saves outputs to `./artifacts/`**
    
    -   `model_logreg.joblib`
        
    -   `model_rf.joblib`
        
    -   `metrics.json`
        

----------

## Repository Contents

-   `otdr_ml_pipeline.ipynb` — end-to-end reproducible notebook
    
-   `requirements.txt` — dependencies
    
-   `README.md` — this file
    
-   `artifacts/` — generated after running the notebook (models + metrics)
    

----------

## Notes / Limitations

-   The dataset is synthetic and designed to mimic OTDR trace patterns with noise and overlap.
    
-   Future work should validate on real OTDR trace archives and monitor performance drift across settings/devices.
