# Machine Learning Basics & Google Colab Environment

This repository provides a standardized, dual-compatible environment for Machine Learning projects, designed to work smoothly both **locally** (via VS Code / Antigravity IDE / Jupyter) and on **Google Colab**.

---

## 🚀 Quick Start (Local Setup)

The virtual environment `.venv` is configured with all essential Data Science and Machine Learning packages.

### 1. Activate the Virtual Environment

- **PowerShell (Windows)**:
  ```powershell
  .venv\Scripts\Activate.ps1
  ```
  *(If execution policies prevent running scripts, run `Set-ExecutionPolicy -Scope Process -ExecutionPolicy Bypass` first)*

- **Command Prompt (cmd.exe)**:
  ```cmd
  .venv\Scripts\activate.bat
  ```

- **Git Bash / WSL / Linux / macOS**:
  ```bash
  source .venv/bin/activate # or source .venv/Scripts/activate
  ```

### 2. Selecting the Kernel in VS Code / Antigravity IDE

1. Open any `.ipynb` notebook (e.g., [`numpy.ipynb`](file:///c:/Users/Debarghya2/Desktop/MACHINE_lEARNING_BASICS/numpy.ipynb) or [`00_environment_verification.ipynb`](file:///c:/Users/Debarghya2/Desktop/MACHINE_lEARNING_BASICS/00_environment_verification.ipynb)).
2. Click on the kernel selector at the top-right corner of the editor.
3. Select **Python Environments...** -> **Python (ML Basics)** or point directly to `.venv\Scripts\python.exe`.

---

## ☁️ Google Colab Compatibility Guide

### 1. Dual-Environment Detection Snippet
Paste this block at the top of your notebooks so the code automatically adapts whether running on Google Colab or locally:

```python
import sys

# Check if running in Google Colab
IN_COLAB = 'google.colab' in sys.modules

if IN_COLAB:
    print("Running in Google Colab environment")
    # Uncomment if your data is stored in Google Drive:
    # from google.colab import drive
    # drive.mount('/content/drive')
    DATA_DIR = "/content/data"
else:
    print("Running in local environment")
    DATA_DIR = "./data"
```

### 2. "Open in Colab" Badges
Each notebook can be launched directly in Google Colab with one click:

- **Verification Notebook**:
  [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/DebarghyaAich/Machine_Learning_Basics/blob/main/00_environment_verification.ipynb)

- **NumPy Basics Notebook**:
  [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/DebarghyaAich/Machine_Learning_Basics/blob/main/numpy.ipynb)

Syntax template for new notebooks:
```markdown
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/DebarghyaAich/Machine_Learning_Basics/blob/main/<NOTEBOOK_NAME>.ipynb)
```

Replace `<YOUR_GITHUB_USERNAME>` and `<NOTEBOOK_NAME>` with your repository details.

---

## 📦 Installed Packages & Ecosystem

| Category | Libraries Included |
|---|---|
| **Numerical & Scientific** | `numpy`, `scipy`, `pandas` |
| **Data Visualization** | `matplotlib`, `seaborn`, `plotly` |
| **Machine Learning** | `scikit-learn`, `statsmodels`, `joblib` |
| **Interactive Notebooks** | `ipykernel`, `ipywidgets`, `notebook`, `nbformat` |
| **Utilities** | `tqdm`, `python-dotenv` |

*(Optional Deep Learning: PyTorch and TensorFlow can be added on-demand by uncommenting lines in [`requirements.txt`](file:///c:/Users/Debarghya2/Desktop/MACHINE_lEARNING_BASICS/requirements.txt))*

---

## 📁 Recommended Project Structure

```text
MACHINE_LEARNING_BASICS/
├── .venv/                     # Isolated Python virtual environment (ignored in git)
├── .vscode/
│   └── settings.json          # Automatic interpreter and notebook configuration
├── data/                      # Datasets (raw / processed)
├── models/                    # Saved models (.joblib / .pkl)
├── notebooks/                 # Organized exploratory & tutorial notebooks
├── requirements.txt           # Python dependency specifications
├── .gitignore                 # Git ignore rules for ML/Python
├── README.md                  # Project documentation & Colab guides
└── 00_environment_verification.ipynb # Environment test & starter pipeline
```
